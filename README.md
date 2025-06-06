class TodoApp:
    def __init__(self):
        self.tasks = []

    def display_tasks(self):
        if not self.tasks:
            print("Your to-do list is empty!")
        else:
            print("\nTo-Do List:")
            for idx, task in enumerate(self.tasks, 1):
                print(f"{idx}. {task}")

    def add_task(self, task):
        self.tasks.append(task)
        print(f"Task '{task}' added successfully!")

    def delete_task(self, task_num):
        if 0 < task_num <= len(self.tasks):
            deleted_task = self.tasks.pop(task_num - 1)
            print(f"Task '{deleted_task}' deleted successfully!")
        else:
            print("Invalid task number!")

    def run(self):
        while True:
            print("\n--- To-Do List Application ---")
            print("1. View tasks")
            print("2. Add a task")
            print("3. Delete a task")
            print("4. Exit")

            choice = input("Choose an option: ")

            if choice == '1':
                self.display_tasks()
            elif choice == '2':
                task = input("Enter the task to add: ")
                self.add_task(task)
            elif choice == '3':
                self.display_tasks()
                task_num = int(input("Enter task number to delete: "))
                self.delete_task(task_num)
            elif choice == '4':
                print("Exiting the application...")
                break
            else:
                print("Invalid choice, please try again.")

if __name__ == "__main__":
    app = TodoApp()
    app.run()
