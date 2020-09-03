Hash Table: is a colllection of items, which are stored in such a way as to make it easy to find them later
            Each position of the hash table, slots, can hold an item and is named by an integer value starting at 0 (i.e., we have a slot named 0, a slot name 1...)
            Initially, the hash table consists of 0 items (so every slot is empty)
            
            
            We can implement a hash table by using a list with each element initialized to the special Python value None.
            
            The mapping between an item and slot where that item belongs in the hash table is called the hash function.
            
            Hash function - will take any item in the collection and return an integer in the range of slot names, between 0 and m-1
            
                Remainder method - when presented with an item, the hash function is an item divided by the table size, this is then its slot number.
                
                Assume the following list of integer items: 54, 26, 93, 17, 77, 31
                We have preassigned an empty hash table of m = 11
                Our remainder hash function then is: h(item) = item % 11 -----> the remainder is the slot we insert the item to. (i.e. 77 % 11 = 0, therefore 77 is in slot 0)
                
                
Search for an Item: use the hash function to compute the slot name for the item and then check the hash table to see if it is present
                    Big-O for this searching operation is O(1) because a constant amount of time is required to compute the hash value and then index the hash table
                    at that location
                    
                    
 Collision:     when two h(item) are equal to each other (44 % 11 == 77 % 11)
 
 Collision Resolution: 1.) Open Addressing - look into the hash table and try to find another open slot to hold the item that caused the collision
                                                (tries to find the next open slot or address in the hash table)
                                                - Linear probing - start at the original hash value position and then move in a sequential manner through 
                                                  the slots until we encounter the first slot is empty 
                                                - Quadratic probing - use a rehashing function that increments the hash value by 1, 3, 5, 7, 9, and so on
                                            This means that if the first hash value is h, the successive values are h+1, h+4, h+9, h+16, and so on
                       2.) Chaining - allow each slot to hold a reference to a collection of items, i.e., allows many items to exist at the same location in the 
                                      hash table 
                                                  
 Rehashing - the process of looking for another slot after a collision
 
 
 Perfect Hash Table: a hash function that maps each item to a unique slot 
 
 GOAL: To create a hash function with the least amount of collisions, is easy to compute, and evenly distributes the items in the hash table.
 
 
 
                Folding Method: for constructing hash functions begin by dividing the item into equal-size pieces (the last piece may not be of equal size).
                                these values are then added together to give the resulting hash value.
                            
                            
EXAMPLE LOGIC:          If our item was a phone number 436-555-4601
                        Divide the digits in groups of 2 (43, 65, 55, 46, 01)
                        Add, the numbers to get 210
                        If we assume the hash table has 11 slots, we must find the remainder of the 210 / 11 (i.e., 210 % 11 = 1)
                        So, the phone number 436-555-4601 is inserted in slot 1
                        
                        
                 Mid-Square Method: first square the item, and then extract the two middle numbers, then execute then find the remainder
                 
                 
EXAMPLE LOGIC:         If there was an item 44
                       You would square 44, so 44 x 44 = 1936
                       then extract the two middle numbers 93
                       then execute the find the remainder from the extracted two middle numbers from the number of slots
                       lastly insert 1936 to that slot value
                       
                       
                       
 Non-integer numbers can be thought of as a sequence of ordinal values
 For example, the word "cat"
        "c" = 99, "a" = 97, "t" = 116 = 312 
        
        In Python, call the ord(char) value to find the exact ordinal value of each number.
        

                        
              
