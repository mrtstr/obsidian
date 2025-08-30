- two possible cases:
	1) **In-place growth possible**: extend the current space when possible → $\mathcal{O}(1)$ 
	2) **In-place growth not possible**: allocate a new buffer when old buffer cant be extended → $\mathcal{O}(cap)$

1. **In-place growth possible**
    
    - If the allocator finds that the memory block can be extended (there is enough free space _right after it_), it will just enlarge the block in place.
        
    - ✅ No copy needed, pointer stays the same.
        
2. **In-place growth not possible**
    
    - If the adjacent memory is already used, the allocator will:
        
        - Allocate a new larger block somewhere else
            
        - Copy/move the old elements into it
            
        - Free the old block
            
    - ⚠️ This is where the costly copy happens.