## Control Flow Testing

- All paths: often impossible due to large test cases
- Statement coverage
    - Weakest, vulnerable to bugs and dead code.
- Branch coverage: mostly appear in tests

- Path testing techniques: doesn't count if the program contains mistakes in the code.

## Predicate Coverage

- Predicate: a statement that returns a boolean value.
- Predicate coverage: just two test cases to make p to be true and false.
- Clause coverage: each clause in the predicate to be true and false at least once.
- Combinatorial coverage: 2^n test cases, where n is the number of clauses in the predicate.
- Active clause coverage: each active clause in the predicate to be true and false at least once.

### a or (b and c) case

- GACC: 
    - a is main clause: b and c = false
    - b is main clause: a = false, c = true
    - c is main clause: a = false, b = true
    - test cases: a = false, b = true, c = true, a = true, b = false, c = false
- RACC:
    - 4 tests


