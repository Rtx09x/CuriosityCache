
---

**The Starting Point:**

- Thought about converting text to Morse code (. and -).
    
- Representing Morse as binary (0 and 1).
    
- Idea: Could this be smaller than standard 8-bit ASCII? Morse uses variable lengths (E='.'=1 bit, T='-'=1 bit, but others are longer).
    

**First Abstraction Idea:**

- Could we then take this Morse-binary string and compress it further?
    
- Maybe find patterns in the 0s and 1s representing dots and dashes?
    

**Why it's Limited / Where it Leads:**

- Morse itself isn't optimized purely for binary storage size.
    
- This quickly led to the bigger idea of [[The Recursive Abstraction Idea]], not just tied to Morse.
    
- It immediately bumps into issues of how to represent the patterns without ambiguity, leading to [[The Core Problem Representing 4 States with 2 Symbols]].