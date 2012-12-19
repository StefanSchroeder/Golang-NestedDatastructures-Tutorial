# Map of Arrays/Slices #

Create nested map of arrays

    moa := map[string][2]string{
      "Jan": [2]string{"a", "b"}, 
      "Feb": [2]string{"c", "d"}, 
    }

Create nested map of slices

    mos := map[string][]string{
      "Apr": []string{"a", "b"}, 
      "May": []string{"c", "d"}, 
    }

Add an array.

    moa["Mar"] = [2]string{"g", "h"}
    mos["Jun"] = []string{"g", "h"}

Delete one map entry

    delete(moa, "Jan")
    delete(mos, "Apr")
 
    mos["May"][0] = "Another"
	
Modify an entry in one of the nested maps.
// Doesn't work! Is a copy: moa["Mar"][0] = "Illegal"
	
    temp := moa["Mar"]
    temp[0] = "formerG"
    moa["Mar"] = temp
  
Extract one field

    fmt.Printf("One value in a nested map: %v\n", moa["Feb"][0])
	
Extract one field

    fmt.Printf("One value in a nested map: %v\n", mos["May"][0])

Extract one array

    fmt.Printf("One array: %v\n",moa["Mar"])

Extract one slice
  
    fmt.Printf("One array: %v\n",mos["Jun"])

by element

    fmt.Println("Array -----")
    for i := range(moa) {
      fmt.Printf("(%s) %v\n", i, moa[i])
      for j:=0; j<len(moa[i]); j++ {
        fmt.Printf(" (%s,%d) %v\n", i, j, moa[i][j])
      }
    }
	
by element, same old...

    fmt.Println("Slice -----")
    for i := range(mos) {
      fmt.Printf("(%s) %v\n", i, mos[i])
      for j:=0; j<len(mos[i]); j++ {
        fmt.Printf(" (%s,%d) %v\n", i, j, mos[i][j])
      }
    }

Entire DSC

    fmt.Printf("Entire Map of Arrays: %v\n",moa)
    fmt.Printf("Entire Map of Slices: %v\n",mos)
                                                           
