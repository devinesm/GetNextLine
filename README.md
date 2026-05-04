*This project has been created as part of the 42 curriculum by ipinto-m.*

# GetNextLine

---

## 📝 Description
The **get_next_line** project consists of implementing a function in C that reads a file (or input) line by line.  
Each call to the function returns the next line from the file until reaching the End Of File (EOF).

This project helps develop a deeper understanding of:
- File descriptors and file handling
- Dynamic memory allocation
- Buffer management
- Maintaining state between function calls
---

## 🚀 Instructions

### Compilation
To compile the project:
```bash
cc -Wall -Wextra -Werror -D BUFFER_SIZE=42 get_next_line.c get_next_line_utils.c
```
You can change the value of ```BUFFER_SIZE``` as needed.

### Usage
Basicc usage example:

```c
#include "get_next_line.h"
#include <fcntl.h>
#include <stdio.h>

int main(void)
{
    int fd = open("file.txt", O_RDONLY);
    char *line;

    while ((line = get_next_line(fd)) != NULL)
    {
        printf("%s", line);
        free(line);
    }
    close(fd);
    return (0);
}
```
---

# 📚 Resources

### References
* [Static Variables in C (GeeksforGeeks)](https://www.geeksforgeeks.org/c/static-variables-in-c/): Explanation of static variables in C, essential for maintaining state between function calls in this project.
* [read(2) — Linux Manual Page (Man7.org)](https://man7.org/linux/man-pages/man2/read.2.html): Official documentation of the `read` system call, which is central to file reading operations in get_next_line.
* [42 Norminette Documentation](https://github.com/42School/norminette): Guide to the coding standards enforced by the 42 Network.
---

### Use of AI
For this project, Artificial Intelligence was used as an educational assistant for the following tasks:
* **Logic Clarification:** Assisting in the understanding of file descriptors, static variables, and buffer management for line-by-line file reading.
* **Edge Case Identification:** Generating test scenarios involving empty files, files without newline characters, multiple file descriptors, and varying BUFFER_SIZE values.
* **Memory Management Guidance:** Helping clarify proper allocation and deallocation strategies to avoid memory leaks.
* **Documentation Formatting:** Structuring and proofreading this README.md file to ensure it meets project requirements and professional standards.
* **Note:** All project code was implemented manually. AI was used exclusively to clarify concepts and assist with documentation, ensuring the learning process remained central to the project.
