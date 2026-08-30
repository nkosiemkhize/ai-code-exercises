My Notes for Task Manager Codebase

Initial Understanding
What I understood initially was that all I knew was this is “Task Management System” written in python. I thought the folder structure was complicated and I had no Idea where things like creating a task or updating its status actually happened in the code 

What I understand now
I understand now that the project is actually small and simple once you know how it is structured. Its command-line app with four main files, and no outside libraries just plain Python.
•	app.py  only reads what you type in the terminal and prints results no real logic\
•	task_manager.py  does the actual work like creating tasks, updating them etc.
•	storage.py saves and loads tasks from a file called tasks.json
•	models.py defines what a task looks like plus the status and priority options


The Most Useful Insight from Each Prompt
•	When I took a look at the project structure my biggest realization was that app.py doesn’t contain any real logic it just takes command and hands it off that is when I knew to always look one level deeper to find where things actually happen. 
•	Running the code myself, at first I had no idea what I was running and I was using PowerShell terminal which I am not familiar with my VS Code terminal is giving me an error so this was also a learning curve for me .
•	I created a task, checked the JSON file, marked it as “done” and checked the file again. That is how I noticed that marking a task “done” is treated differently from other status changes it also  saves a completed_at timestamp, which no other status change does. I only found this because I checked the actual file not from guessing it from reading.


My Plan for Adding CSV Export

I would follow the same style as the rest of the code:
•	In storage.py add a new method called  export_csv() that writes all tasks to a CSV file. I’d copy the same style as the existing save() method, including how it handles errors.
•	In task_manager.py add method called export_csv() that gets all the tasks using a method that already exist and passes them to the new storage.py method
•	In app.py add a new command called “export”, the same way “create” and “list” are already set up.
•	I would not need to change models.py at all. Task  already has all the information a CSV file would need
Note to ask my team:
Should this CSV code live inside storage.py or should it be its own separate file?

Strategies to Use Next Time
•	I will pick one action like “create a task” and follow it step through the code instead of trying to read every file top to bottom. That is a faster way to understand how everything connects
•	I will run the code and check the actual output more instead of just reading and assuming I understood it. I caught a real detail this way that I would have missed otherwise.
•	I’d search using the actual words used in the code not a general description of the feature.
•	Before searching for a feature, I’d double check whether it already exists or if I am actually being asked to build it. These are two very different tasks.
•	I’d keep asking simple questions like “which file is actually responsible for this” every time I read a new code instead of assuming.
