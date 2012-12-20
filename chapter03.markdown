# Array of Maps #

    var arr = [2]map[string]int{} // Create an array with empty maps in it.

    aom1 := map[string]int{ "one": 1, "two": 4, "three": 9, }
    arr[0] = aom1 // put map into the array 
    arr[1] = map[string]int{ "eight":64, "nine": 81, } // put another map into the array

Overwrite a value in the first 

    arr[0]["one"] = 99

Overwrite one map

    arr[1] = map[string]int{"Snake": 0, "Lion": 4, "Penguin": 2}

Get first record.

    fmt.Printf("First record: %v\n", arr[0])

Print entire array of maps.

    fmt.Printf("Entire array of maps: %v\n", arr)

Print entire array of maps element by element

    for i:=0; i<len(arr) ; i++ {
      fmt.Printf("(i=%d) %v\n", i, arr[i])
      for j := range(arr[i]) {
        fmt.Printf("(%d) %s => %d\n", i, j, arr[i][j])
      }
      fmt.Printf("\n")
    }

Second example. All in one.

  	aomB1 := [2]map[string]int{ map[string]int{"one": 1}, map[string]int{"two" : 2,}, }
  	aomB3 := [...]map[string]int{ map[string]int{"one": 1}, map[string]int{"two" : 2,}, }
  	aomB2 := []map[string]int{ map[string]int{"one": 1}, map[string]int{"two" : 2,}, }
  	fmt.Printf("Entire DSC: %v\n", aomB1)
  	fmt.Printf("Entire DSC: %v\n", aomB2)
  	fmt.Printf("Entire DSC: %v\n", aomB3)
