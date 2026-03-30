# C++ Module 05 — Repetition and Exceptions

## Subject
Model a bureaucratic system in C++98 with exception handling.

---

## Exercises

### ex00 — Bureaucrat
- `Bureaucrat` class: constant name + grade (1 = highest, 150 = lowest)
- Nested exceptions: `GradeTooHighException`, `GradeTooLowException`
- Methods: `getName()`, `getGrade()`, `incrementGrade()`, `decrementGrade()`
- `operator<<` overload: `<name>, bureaucrat grade <grade>.`

### ex01 — Form
- `Form` class: constant name, signed (bool), grade required to sign, grade required to execute
- Exceptions: `Form::GradeTooHighException`, `Form::GradeTooLowException`
- `Form::beSigned(Bureaucrat&)`: signs if grade is high enough, otherwise throws
- `Bureaucrat::signForm(Form&)`: calls `beSigned()`, prints success or reason for failure

### ex02 — AForm + Concrete Forms
- `Form` becomes `AForm` (abstract class) with `execute(Bureaucrat const& executor) const`
- Check before execution: form is signed + bureaucrat grade is sufficient

| Class | Sign | Exec | Action |
|---|---|---|---|
| `ShrubberyCreationForm` | 145 | 137 | Creates `<target>_shrubbery` with ASCII trees |
| `RobotomyRequestForm` | 72 | 45 | Robotomizes `<target>` (50% success, 50% failure) |
| `PresidentialPardonForm` | 25 | 5 | `<target>` has been pardoned by Zaphod Beeblebrox |

- `Bureaucrat::executeForm(AForm const&)`: attempts execution, prints result

---

## Key Rules
- C++98 only (`-Wall -Wextra -Werror -std=c++98`)
- Orthodox Canonical Form required for all classes (except exception classes)
- No `using namespace`, no `friend`, no STL (allowed only in modules 08/09)
- No `printf`, `alloc`, `free`
- Include guards on all headers
- No implementation in headers (except templates)
- No memory leaks (`new` → `delete`)
