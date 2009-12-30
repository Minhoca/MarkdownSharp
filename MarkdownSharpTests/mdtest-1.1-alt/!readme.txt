﻿
/// <summary>
/// iterates through all the test files in a given folder and generates file-based output 
/// this is essentially the same as running the unit tests, but with diff-able results
/// </summary>
/// <remarks>
/// two files should be present for each test:
/// 
/// test_name.text         -- input (raw markdown)
/// test_name.html         -- output (expected cooked html output from reference markdown engine)
/// 
/// this file will be generated if, and ONLY IF, the expected output does not match the actual output:
/// 
/// test_name.xxxx.actual.html  -- actual output (actual cooked html output from our markdown c# engine)
///                             -- xxxx is the 16-bit CRC checksum of the file contents; this is included
///                                so you can tell if the contents of a failing test have changed
/// </remarks>

same as mdtest-1.1, but:

* remove any non-significant whitespace or extra paragraph differences
  (there are only two as I recall; not sure why, but frankly who cares)
  
* comment out any edge conditions we aren't dealing with yet; search for
  the string "omitted:" to see what those are