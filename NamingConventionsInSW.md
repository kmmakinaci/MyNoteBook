# Naming Conventions in Your Software Project

These guidelines help maintain consistency and readability across C++ projects following Google's style.

## Google’s C++ coding style conventions for naming

### 1. **Project Naming**

- Projects are generally named in **lowercase** with words separated by underscores (`_`).
- Example: `my_project`, `data_processing`

### 2. **Folder Naming**

- Folders follow a similar convention as projects, using **lowercase** letters and underscores for separation.
- Example: `utils`, `network_services`

### 3. **Class Naming**

- Class names are written in **PascalCase** (also known as UpperCamelCase), meaning the first letter of each word is capitalized.
- Class names should be descriptive nouns.
- Example: `NetworkManager`, `UserDatabase`

### 4. **Variable Naming**

- Local variables, function parameters, and data members are written in **lowercase_with_underscores**.

- Member variables (inside a class) often use a trailing underscore (`_`).

- Example:

  ```
  int total_count;
  int data_value_;
  ```

### 5. **Constant Variables**

- Constant variables use **kPascalCase**, starting with a `k`.

- Example:

  ```
  const int kMaxValue = 100;
  ```

### 6. **Function Naming**

- Functions and methods are written in **lowerCamelCase**, where the first word is lowercase and subsequent words are capitalized.

- Example:

  ```
  void processData();
  int calculateSum();
  ```

### 7. **Type Naming (Typedefs, Enums, Structs, etc.)**

- Types (including `typedef`, `enum`, `struct`, and `using`) are written in **PascalCase**.

- Example:

  ```
  typedef int MyInteger;
  enum StatusCode { OK, ERROR };
  ```



## Differences between Linux and Google C++ guidelines

The primary differences between **Google C++ style** and **Linux kernel coding style** lie in their approach to code formatting, naming conventions, and general coding philosophy. Below is a comparison of some key aspects:

### 1. **Indentation**

- **Google Style:**

  - Indents are **2 spaces** (no tabs).
  - Uses **spaces** consistently.

  ```
  void myFunction() {
    if (condition) {
      // 2 spaces indent
      execute();
    }
  }
  ```

- **Linux Style:**

  - Indents are **8 spaces** or **1 tab**.
  - Uses **tabs** for indentation, but **spaces** for alignment.

  ```
  void my_function(void)
  {
      if (condition) {
          /* 1 tab = 8 spaces */
          execute();
      }
  }
  ```

### 2. **Braces**

- **Google Style:**

  - Braces go on the **same line** as the control statement or function signature (Allman or K&R style).

  ```
  void myFunction() {
    if (condition) {
      execute();
    }
  }
  ```

- **Linux Style:**

  - Braces go on the **next line** after the control statement or function signature.

  ```
  void my_function(void)
  {
      if (condition) {
          execute();
      }
  }
  ```

### 3. **Function Naming**

- **Google Style:**

  - Function names use **lowerCamelCase**.

  ```
  void processData();
  ```

- **Linux Style:**

  - Function names use **lowercase_with_underscores**.

  ```
  void process_data(void);
  ```

### 4. **Variable Naming**

- **Google Style:**

  - Variable names use **lower_case_with_underscores**.
  - Member variables often have a trailing underscore (`_`).

  ```
  int total_count;
  int data_value_;
  ```

- **Linux Style:**

  - Variable names use **lowercase_with_underscores**, but the style is more consistent across all variables.

  ```
  int total_count;
  int data_value;
  ```

### 5. **Line Length**

- **Google Style:**

  - Line length should not exceed **80 columns**, though in practice, **100 columns** is considered acceptable.

  ```
  // If the line is too long, break it up.
  some_really_long_function_name_with_many_parameters(
      param1, param2, param3, param4);
  ```

- **Linux Style:**

  - Enforces a strict **80-column limit**.

  ```
  some_function_with_many_parameters(param1, param2,
                                     param3, param4);
  ```

### 6. **Commenting**

- **Google Style:**

  - Uses `//` for single-line comments and `/* ... */` for block comments.
  - Comments generally precede the code they're describing, and Doxygen-style comments are often used for function documentation.

  ```
  // Processes data and returns the result.
  void processData() {
    /* Handle the case when input is empty */
  }
  ```

- **Linux Style:**

  - Uses C-style `/* ... */` comments more often.
  - Single-line comments are acceptable but less frequent. Block comments are typically used for function documentation.

  ```
  /*
   * Processes data and returns the result.
   */
  void process_data(void)
  {
      /* Handle empty input case */
  }
  ```

### 7. **Whitespace**

- **Google Style:**

  - Google prefers **more compact code** with limited use of whitespace.

  ```
  if (condition) {
    doSomething();
  } else {
    doSomethingElse();
  }
  ```

- **Linux Style:**

  - Linux kernel style often includes **more vertical whitespace** for readability, especially before function definitions.

  ```
  if (condition) {
      do_something();
  } else {
      do_something_else();
  }
  ```

### 8. **Macros**

- **Google Style:**

  - Macros are generally discouraged unless absolutely necessary. Constants should prefer `const` or `constexpr`.

  ```
  constexpr int kMaxValue = 100;
  ```

- **Linux Style:**

  - Macros are widely used in the Linux kernel and are often written in **ALL_CAPS**.

  ```
  #define MAX_VALUE 100
  ```

### 9. **Type Naming**

- **Google Style:**

  - Type names (structs, typedefs, enums) use **PascalCase**.

  ```
  typedef int MyInteger;
  enum StatusCode { OK, ERROR };
  ```

- **Linux Style:**

  - Type names typically use **lowercase_with_underscores**.

  ```
  typedef int my_integer;
  enum status_code { OK, ERROR };
  ```

### 10. **Error Handling**

- **Google Style:**

  - Google prefers **exceptions** in C++ for error handling where applicable, although exceptions may be avoided in performance-critical sections.

  ```
  throw std::runtime_error("Error occurred");
  ```

- **Linux Style:**

  - Linux kernel avoids exceptions and prefers returning **error codes** (typically negative integers).

  ```
  return -ENOMEM;
  ```

### Summary:

- **Google Style** is more focused on C++ specifics with compact and modern coding practices, whereas **Linux Style** is rooted in C and prioritizes readability for large-scale collaborative development.
- Google C++ code tends to be more concise in terms of vertical space, while Linux code has more whitespace to improve readability in a long-term maintenance environment.

These differences reflect the broader goals of each style guide—**Google** for more general-purpose C++ development and **Linux** for a highly collaborative, large-scale kernel project.



## Apply the guideline rule to your project



This process ensures that your code is consistently styled according to the Google C++ standards. You can apply a **pre-commit hook** or other types of hooks (like post-commit) to automatically enforce these naming conventions in your C++ project. This ensures that code commits conform to the Google C++ style guidelines before they are accepted into the repository. Below is a high-level approach on how to implement this:

### 1. **Pre-Commit Hook using `clang-tidy` and `clang-format`:**

Google C++ style can be enforced using tools like `clang-tidy` and `clang-format`, which provide checks for style issues.

#### Steps:

1. **Install `clang-tidy` and `clang-format`:**

   - On Ubuntu: `sudo apt-get install clang-tidy clang-format`
   - On macOS: `brew install clang-format clang-tidy`

2. **Create a `.clang-format` file in the root of your project:** This file specifies the formatting rules. You can use the Google style preset:

   ```
   BasedOnStyle: Google
   ```

3. **Write the Pre-Commit Hook Script:** Create a pre-commit hook that runs `clang-tidy` and `clang-format` on staged files before committing.

   Example `pre-commit` script:

   ```
   #!/bin/sh
   # Run clang-format and clang-tidy on all staged files
   
   # Get a list of staged files that are C++ source files
   FILES=$(git diff --cached --name-only --diff-filter=ACM | grep -E '\.(cpp|hpp|cc|h)$')
   
   if [ "$FILES" = "" ]; then
     exit 0
   fi
   
   echo "Running clang-format and clang-tidy on staged files..."
   
   # Run clang-format and clang-tidy on each file
   for file in $FILES; do
     clang-format -i "$file"
     clang-tidy "$file" -- -std=c++17
     git add "$file"
   done
   
   echo "Done formatting."
   ```

4. **Make the Pre-Commit Hook Executable:** Save the script as `.git/hooks/pre-commit` and make it executable:

   ```
   chmod +x .git/hooks/pre-commit
   ```

### 2. **Using `pre-commit` Framework:**

Alternatively, you can use the `pre-commit` framework to set up the hooks. This is more extensible and easier to maintain in larger projects.

#### Steps:

1. Install the `pre-commit` package:

   ```
   pip install pre-commit
   ```

2. Create a `.pre-commit-config.yaml` in the root of your project:

   ```
   repos:
     - repo: https://github.com/pre-commit/mirrors-clang-format
       rev: v12.0.0  # Adjust to match the clang-format version you want
       hooks:
         - id: clang-format
           args: [--style=google]
   ```

3. Run `pre-commit install` to install the hook.

Now, every time you commit, the pre-commit hook will automatically format your code according to Google's C++ style.