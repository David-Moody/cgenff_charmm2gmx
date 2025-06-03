# Changes

    -
    entry = re.split('\s+', line.lstrip())

    + 
    entry = line.lstrip().split()

'\s+' is incorrect escaping of the \\. This could be fixed by using a raw string r'\s+' or '\\\\s+', as the string is parsed by Python first before being passed to the regex engine.

Even better split by 1 or more whitespace characters is the default algorithm for str.split() in Python so there is no need to use the re module.

- Use context managers for opening files
- for line in f: instead of for line in f.readlines(): No need to read whole file at once, Python handles performant buffering of the file read.
- Swapped calls to exit() inside functions to raise ValueErrors
- Any function that takes self, should be a member of the atomgroup class.
- Add as many type hints as possible
- Add various guard clauses, raising ValueErrors
- Set default None values for variables that are possibly unbound
- Remove unused functions
- Use list comprehensions where it is more readable and reduces explicit typing
- Add an AtomInfo TypedDict to allow type information to passed around correctly
