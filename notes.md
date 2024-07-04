# Workshop Notes


- List packages `pip list`
- `python3 -m pytest tests/test_models.py`
  - python3 -m is required.
  - It ensures:
    - you have access to the imported modules
    - and the path to the tests
  - Without it does not add the current directory to its list of directories
  to search for modules,
- Verbose (-v, --verbose): 
  - `python3 -m pytest tests/test_models.py -v`

