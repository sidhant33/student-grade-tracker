# student-grade-tracker
# Student Grade Tracker

def add_student(students):
    name = input("Enter student name: ")
    if name in students:
        print("Student already exists.")
    else:
        students[name] = []
        print(f"{name} has been added.")

def add_grade(students):
    name = input("Enter student name: ")
    if name not in students:
        print("Student not found.")
        return
    try:
        grade = float(input("Enter grade: "))
        students[name].append(grade)
        print(f"Grade {grade} added for {name}.")
    except ValueError:
        print("Invalid grade input.")

def calculate_averages(students):
    for name, grades in students.items():
        if grades:
            average = sum(grades) / len(grades)
            print(f"{name}'s average grade: {average:.2f}")
        else:
            print(f"{name} has no grades entered.")

def main():
    students = {}
    while True:
        print("\nGrade Tracker Menu:")
        print("1. Add Student")
        print("2. Add Grade")
        print("3. Calculate Averages")
        print("4. Exit")

        choice = input("Choose an option (1-4): ")

        if choice == '1':
            add_student(students)
        elif choice == '2':
            add_grade(students)
        elif choice == '3':
            calculate_averages(students)
        elif choice == '4':
            print("Exiting program.")
            break
        else:
            print("Invalid option. Please choose between 1-4.")

if _name_ == "_main_":
    main()
