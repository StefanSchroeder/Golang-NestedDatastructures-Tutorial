# Arrays of Arrays #

In the first chapter we want to create arrays of arrays.
Because slices and arrays are handled very similarly, slices are handled here as well.

Please note that a complete source code file is available at the same location where you found this markdown page.

## Create ##

Create nested Array Of Array

    aoa := [3][2]string{ [...]string{"a","b"}, [...]string{"c","d"}, [...]string{"e", "f"}, }

Create nested Array Of Slices

    aos := [3][]string{ []string{"a","b"}, []string{"c","d"}, []string{"e", "f"}, }

## Update ##

Set a single entry from nested array

	aoa[1][1] = "OverwrittenInArray"
	aos[1][1] = "OverwrittenInSlice"
	
Put entire array

	aoa[2] = [...]string{"OverwritingInArray", "AnotherInArray"}

Put entire slice

	aos[2] = []string{"OverwritingInSlice", "AnotherInSlice"}

## Retrieve ##

Get one array

	fmt.Printf("The second array is %v.\n", aoa[1])

Prints "The second array is [c OverwrittenInArray]."

Get one slice

	fmt.Printf("The second slice is %v.\n", aos[1])

Prints: "The second slice is [c OverwrittenInSlice]."

Get a single entry from nested array

	fmt.Printf("Entry 2,1 in array is %s.\n", aoa[2][1]) // "f"

Get a single entry from nested slice

	fmt.Printf("Entry 2,1 in slice is %s.\n", aos[2][1]) // "f"

## Print entire Array of Arrays by element ##

	for i:=0; i<len(aoa); i++ {
		fmt.Printf("(%d. array) %v\n", i, aoa[i])
		for j:=0; j<len(aoa[i]); j++ {
			fmt.Printf(" (%d,%d) %v\n", i, j, aoa[i][j])
		}
	}

Prints

	(0. array) [a b]
	 (0,0) a
	 (0,1) b
	(1. array) [c OverwrittenInArray]
	 (1,0) c
	 (1,1) OverwrittenInArray
	(2. array) [OverwritingInArray AnotherInArray]
	 (2,0) OverwritingInArray
	 (2,1) AnotherInArray


## Print entire Array of Slices by element ##

	for i:=0; i<len(aos); i++ {
		fmt.Printf("(%d. slice) %v\n", i, aos[i])
		for j:=0; j<len(aos[i]); j++ {
			fmt.Printf(" (%d,%d) %v\n", i, j, aos[i][j])
		}
	}

Prints

	(0. slice) [a b]
	 (0,0) a
	 (0,1) b
	(1. slice) [c OverwrittenInSlice]
	 (1,0) c
	 (1,1) OverwrittenInSlice
	(2. slice) [OverwritingInSlice AnotherInSlice]
	 (2,0) OverwritingInSlice
	 (2,1) AnotherInSlice
	
## Print the entire Array of Arrays using %v shortcut. ##
	
	fmt.Printf("%v\n", aoa)

Prints

	[[a b] [c OverwrittenInArray] [OverwritingInArray AnotherInArray]]

## Print the entire Array of Slices using %v shortcut. ##

	fmt.Printf("%v\n", aos)

Prints

	[[a b] [c OverwrittenInSlice] [OverwritingInSlice AnotherInSlice]]

        
