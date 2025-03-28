
---

**The Concept:**

- Take a binary string.
    
- Find repeating patterns (e.g., 00, 01, 10, 11, or longer sequences).
    
- Replace these patterns with new, shorter symbols (Abstract Layer 1).
    
- Store a "map" or "dictionary" for this replacement.
    
- **Crucially:** Take the new string of symbols and repeat the process. Find patterns in the symbols, replace them with even fewer symbols (Abstract Layer 2), store that map.
    
- Keep doing this recursively until you ideally end up with a very small piece of data (maybe even one symbol?) plus a set of abstraction maps.
    

**The Goal:** Extreme, potentially infinite lossless compression. The idea was that the final data + the maps would be tiny compared to the original.

**The Breakdown / Why it Hits a Wall:**

- **The Mapping Problem:** How do you represent the new symbols? If you use the original symbols (0 and 1), you immediately run into [[The Core Problem Representing 4 States with 2 Symbols]] of ambiguity and needing more symbols than you have.
    
- **Data Inflation:** If you introduce new symbols (like A, B, C, D, or spaces), the alphabet keeps growing. The abstraction maps themselves become data that needs storing and potentially compressing, often growing larger than the supposed savings. It starts inflating the data.
    
- **Ambiguity & Corruption:** As seen in [[Exploring Solutions Encoding Tricks]], simple replacement without clear separators or structure leads to data corruption during decompression because you don't know where one symbol ends and the next begins.
    
- **Combinatorial Explosion:** Each layer of abstraction potentially creates more unique combinations than the layer before, requiring an ever-larger symbol set or map, leading back to [[The Shannon Wall Combinatorial Explosion & Entropy Limit]].
    