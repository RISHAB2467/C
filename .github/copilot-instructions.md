# C Programming Educational Repository

Always reference these instructions first and fallback to search or bash commands only when you encounter unexpected information that does not match the info here.

## Working Effectively

### Environment Setup
- Ensure GCC is installed: `gcc --version` (should show GCC 13.3.0 or later)
- All programs use standard C library only - no external dependencies required
- Programs are designed for Linux/Unix environments

### Building and Testing
- **NEVER CANCEL**: Compilation is very fast (< 1 second for all programs). Set timeout to 60+ seconds for safety.
- Build individual programs: `cd week1 && gcc -Wall -Wextra -std=c99 -o program_name program_name.c`
- Build all programs at once:
  ```bash
  cd week1
  for file in *.c; do gcc -Wall -Wextra -std=c99 -o "${file%.c}" "$file"; done
  ```
- **Build time**: < 1 second for all 10 programs combined. NEVER CANCEL - compilation is extremely fast.
- Clean up executables: `cd week1 && rm -f Rotate_array check_palindrome check_sorting frequency_of_element insert_element largest_element move_zero_to_end reversa_array reverse_string second_largest_element`

### Running Programs
- All programs are interactive console applications that read from stdin
- Run any program: `cd week1 && ./program_name`
- Programs expect user input as prompted (array sizes, elements, strings, etc.)
- Test with sample input: `echo -e "input_data" | ./program_name`

### Validation Scenarios
Always test program functionality after making changes:

#### Array Programs
```bash
cd week1

# Test insert_element
echo -e "3\n1 2 3\n4" | ./insert_element
# Expected: "Array after insertion: 1 2 3 4"

# Test largest_element
echo -e "5\n10 25 3 45 8" | ./largest_element  
# Expected: "The largest element is: 45"

# Test move_zero_to_end
echo -e "6\n1 0 2 0 3 0" | ./move_zero_to_end
# Expected: "Array after moving all zeros to the end: 1 2 3 0 0 0"

# Test check_sorting
echo -e "5\n1 2 3 4 5" | ./check_sorting
# Expected: "The array is sorted in ascending order."

# Test reversa_array
echo -e "4\n1 2 3 4" | ./reversa_array
# Expected: "Reversed array: 4 3 2 1"
```

#### String Programs  
```bash
# Test check_palindrome
echo "racecar" | ./check_palindrome
# Expected: "The string is a palindrome."

# Test reverse_string
echo "hello" | ./reverse_string
# Expected: "Reversed string: olleh"
```

### Known Issues and Warnings
- `check_palindrome.c` and `reverse_string.c` use deprecated `gets()` function
- This causes compilation warnings but programs work correctly
- Warnings are expected and do not indicate build failure
- **Do not attempt to "fix" these warnings** unless specifically asked - they are part of the educational content

### Repository Structure
```
/
├── README.md           # Basic repository description
├── week1/             # Week 1 programming exercises (10 programs)
│   ├── insert_element.c
│   ├── largest_element.c
│   ├── second_largest_element.c
│   ├── move_zero_to_end.c
│   ├── Rotate_array.c
│   ├── check_sorting.c
│   ├── reverse_string.c
│   ├── check_palindrome.c
│   ├── frequency_of_element.c
│   └── reversa_array.c
└── .github/
    └── copilot-instructions.md
```

## Common Tasks

### Adding New Programs
- Create new `.c` file in appropriate week directory
- Follow existing naming convention (lowercase with underscores)
- Include descriptive comment at top of file
- Test compilation and functionality before committing

### Modifying Existing Programs
- Always compile and test the specific program after changes
- Use sample inputs to verify functionality
- Check that output format matches expected patterns
- Programs should remain interactive console applications

### Repository Information Cache
To save time on common inquiries, here are frequently needed details:

#### Repository Contents
```bash
ls -la /
README.md
week1/

ls -la week1/
Rotate_array.c
check_palindrome.c  
check_sorting.c
frequency_of_element.c
insert_element.c
largest_element.c
move_zero_to_end.c
reversa_array.c
reverse_string.c
second_largest_element.c
```

#### Program Descriptions
1. `insert_element.c` - Insert element at end of array
2. `largest_element.c` - Find largest element in array  
3. `second_largest_element.c` - Find second largest element
4. `move_zero_to_end.c` - Move all zeros to end of array
5. `Rotate_array.c` - Rotate array elements by one position
6. `check_sorting.c` - Check if array is sorted in ascending order
7. `reverse_string.c` - Reverse a string (uses gets())
8. `check_palindrome.c` - Check if string is palindrome (uses gets())
9. `frequency_of_element.c` - Count frequency of array elements
10. `reversa_array.c` - Reverse array elements

### Development Workflow
1. Navigate to repository root: `cd /path/to/C`
2. Make changes to programs in `week1/` directory
3. Compile changed programs: `gcc -Wall -Wextra -std=c99 -o program_name program_name.c`
4. Test with sample inputs to verify functionality
5. Clean up executables before committing changes

### Performance Expectations
- **Compilation**: < 1 second for all programs (NEVER CANCEL)
- **Execution**: Immediate response for all test inputs
- **Memory**: All programs use fixed-size arrays, no dynamic allocation
- **Input size**: Programs designed for small educational datasets (< 100 elements)

This repository contains educational C programming exercises focused on fundamental array and string operations. All programs are standalone and designed for learning basic programming concepts.