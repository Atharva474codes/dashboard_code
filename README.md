# A basic To-Do List application

class TodoList:
    def __init__(self):
        self.tasks = []

    def add_task(self, task):
        self.tasks.append(task)
        print(f"Task '{task}' added.")

    def remove_task(self, task):
        if task in self.tasks:
            self.tasks.remove(task)
            print(f"Task '{task}' removed.")
        else:
            print(f"Task '{task}' not found.")

    def show_tasks(self):
        if not self.tasks:
            print("No tasks to show.")
        else:
            print("\nYour To-Do List:")
            for idx, task in enumerate(self.tasks, start=1):
                print(f"{idx}. {task}")

    def mark_done(self, task):
        if task in self.tasks:
            self.tasks.remove(task)
            print(f"Task '{task}' marked as done.")
        else:
            print(f"Task '{task}' not found.")

def main():
    todo_list = TodoList()
    while True:
        print("\nOptions: ")
        print("1. Add Task")
        print("2. Remove Task")
        print("3. Show Tasks")
        print("4. Mark Task as Done")
        print("5. Exit")
        choice = input("Choose an option: ")

        if choice == '1':
            task = input("Enter the task: ")
            todo_list.add_task(task)
        elif choice == '2':
            task = input("Enter the task to remove: ")
            todo_list.remove_task(task)
        elif choice == '3':
            todo_list.show_tasks()
        elif choice == '4':
            task = input("Enter the task to mark as done: ")
            todo_list.mark_done(task)
        elif choice == '5':
            print("Exiting...")
            break
        else:
            print("Invalid choice, try again.")

if __name__ == "__main__":
    main()
