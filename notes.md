# Workshop Notes

https://scientificcomputingcharite.github.io/2024-06-24-python-intermediate-development/index.html

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

    - table driven tests in python
      - https://docs.pytest.org/en/7.1.x/how-to/parametrize.html
        ```py
          @pytest.mark.parametrize(
          "test, expected",
          [
          ([ [0, 0], [0, 0], [0, 0] ], [0, 0]),
          ([ [1, 2], [3, 4], [5, 6] ], [3, 4]),
          ])
          def test_daily_mean(test, expected):
          """Test mean function works for array of zeroes and positive integers."""
          from inflammation.models import daily_mean
          npt.assert_array_equal(daily_mean(np.array(test)), np.array(expected))
          ```
      - https://lorenzopeppoloni.com/tabledriventestspy/
        ```py
        import unittest
    
        class TestMySort(unittest.TestCase):
          def test_my_sort(self):
            testcases = [
              {"name": "empty_slice", "input": [], "expected": [],},
              {"name": "already_sorted","input": [1, 4, 6, 8],"expected": [1, 4, 6, 8],},
              {"name": "not_sorted", "input": [1, 8, 3, 5], "expected": [1, 3, 5, 8],},
            ]

            for case in testcases:
              actual = my_sort(case["input"])
              self.assertListEqual(
                  case["expected"],
                      actual,
                      "failed test {} expected {}, actual {}".format(
                          case["name"], case["expected"], actual
                      ),
                  )
          ```
        
- install pytest-cov for coverage reports