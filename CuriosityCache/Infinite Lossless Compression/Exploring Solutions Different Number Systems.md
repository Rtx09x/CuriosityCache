
---

Another idea was to escape binary limitations by converting to higher bases:

1. **Binary (Base-2):** Our starting point (0, 1). Problem: [[The Core Problem Representing 4 States with 2 Symbols|4 combinations need representing]].
    
2. **Quaternary (Base-4):** Uses symbols 0, 1, 2, 3.
    
    - **Idea:** Maybe map 2 binary bits directly to 1 quaternary digit (00->0, 01->1, 10->2, 11->3). Seems efficient!
        
    - **The Catch:** Now, if we want to compress quaternary data further by looking at pairs, we have 4 symbols, leading to 4² = **16 possible combinations**. We now need to represent 16 states using only 4 symbols (0,1,2,3). The problem just got worse, not better. We hit the same wall at the next level, but bigger.
        
3. **Octal (Base-8):** Uses 0-7.
    
    - **Idea:** Map 3 binary bits to 1 octal digit. Or try mapping quaternary pairs (16 combinations) to octal (8 symbols).
        
    - **The Catch:** Still faces the same issue. Mapping 16 states onto 8 symbols losslessly is impossible. If compressing octal pairs, you have 8² = **64 combinations** needing 8 symbols. Explosion continues.
        
4. **Hexadecimal (Base-16):** Uses 0-9, A-F. (16 symbols).
    
    - **The Catch:** 16² = **256 combinations** needing 16 symbols.
        
5. **Base-64:** Uses 64 symbols (A-Z, a-z, 0-9, +, /).
    
    - **The Catch:** 64² = **4096 combinations** needing 64 symbols.
        
6. **ASCII (effectively Base-256 for 8-bit):**
    
    - **Idea:** Maybe convert the highly abstract number/symbol into text/ASCII?
        
    - **The Catch:** Just represents the number using 8 bits per character. It's encoding, not compression in this context. It usually inflates the data size compared to a compact binary representation of the same number.
        

**Conclusion:** Changing number systems is just **re-encoding**. It doesn't fundamentally change the amount of information or solve [[The Core Problem Representing 4 States with 2 Symbols]]. Each step up in base makes the subsequent combinatorial explosion larger, demonstrating [[The Shannon Wall Combinatorial Explosion & Entropy Limit]] even more clearly. Direct conversion between higher bases without involving binary is possible mathematically but doesn't bypass this core issue for compression.