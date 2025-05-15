# student_management.py

students = []

def add_student():
    student_id = input("Enter student ID: ")
    name = input("Enter student name: ")
    age = input("Enter student age: ")
    course = input("Enter course: ")
    student = {
        "id": student_id,
        "name": name,
        "age": age,
        "course": course
    }
    students.append(student)
    print("Student added successfully!\n")

def view_students():
    if not students:
        print("No students found.\n")
        return
    print("\n--- Student List ---")
    for s in students:
        print(f"ID: {s['id']}, Name: {s['name']}, Age: {s['age']}, Course: {s['course']}")
    print()

def search_student():
    student_id = input("Enter student ID to search: ")
    for s in students:
        if s['id'] == student_id:
            print(f"Found: ID: {s['id']}, Name: {s['name']}, Age: {s['age']}, Course: {s['course']}\n")
            return
    print("Student not found.\n")

def delete_student():
    student_id = input("Enter student ID to delete: ")
    for i, s in enumerate(students):
        if s['id'] == student_id:
            del students[i]
            print("Student deleted successfully.\n")
            return
    print("Student not found.\n")

def update_student():
    student_id = input("Enter student ID to update: ")
    for s in students:
        if s['id'] == student_id:
            s['name'] = input("Enter new name: ")
            s['age'] = input("Enter new age: ")
            s['course'] = input("Enter new course: ")
            print("Student updated successfully.\n")
            return
    print("Student not found.\n")

def menu():
    while True:
        print("=== Student Management System ===")
        print("1. Add Student")
        print("2. View Students")
        print("3. Search Student")
        print("4. Update Student")
        print("5. Delete Student")
        print("6. Exit")
        choice = input("Enter your choice (1-6): ")

        if choice == '1':
            add_student()
        elif choice == '2':
            view_students()
        elif choice == '3':
            search_student()
        elif choice == '4':
            update_student()
        elif choice == '5':
            delete_student()
        elif choice == '6':
            print("Exiting...")
            break
        else:
            print("Invalid choice. Please try again.\n")

if __name__ == "__main__":
    menu().
