# IMPORTANT INFORMATION FOR USE
Copy this folder and continue working in main.cpp

Note that any c++ files should be contained in the src folder

If wanting to delete the main.cpp (or any other c++ file), and replace it with a different c++ file, make sure to **delete _every_ instance of "(name of cpp file).o"** , make sure to also check in bin/debug and bin/release.

Whenever updating the project with **any** graphics, audio, etc in the res folder, **make sure to copy the res folder into bin/debug and bin/release** .

## How to change the names of the sublime project and workspace

Step 1:

Delete the already existing .sublime-project and .sublime-workspace files in the folder

Step 2:

Open up sublime text (the actual application, not any sublime project)

Step 3:

In the blank file that should appear, paste in this code:

```json
{
	"folders":
	[
		{
			"path": "bin/..",
			"file_exclude_patterns": ["*.sublime-project"]
		}
	],

	"build_systems":
	[
		{
			"name": "Build Debug",
			"working_dir": "${project_path}",
			"cmd": "g++ -c src/*.cpp -std=c++14 -g -Wall -m64 -I include -I C:/SDL2-w64/include && g++ *.o -o bin/debug/main -L C:/SDL2-w64/lib -lmingw32 -lSDL2main -lSDL2 -lSDL2_image && start bin/debug/main",
			"selector": "source.c++",
			"shell": true
		},
		{
			"name": "Build Release",
			"working_dir": "${project_path}",
			"cmd": "g++ -c src/*.cpp -std=c++14 -O3 -Wall -m64 -I include -I C:/SDL2-w64/include && g++ *.o -o bin/release/main -s -L C:/SDL2-w64/lib -lmingw32 -lSDL2main -lSDL2 -lSDL2_image && start bin/release/main",
			"selector": "source.c++",
			"shell": true
		}

	]
}
```

Step 4:

Hit ctrl + S, which should pop up a dialogue for where to save the file

Step 5:

Navigate to your project folder, and make sure the "Save as type" is set to "All Files"

Step 6:

Name the file: "(name that you want it to have, for example the name of your project).sublime-project", and hit "Save"

Step 7:

Close out of Sublime Text (fully) and navigate to your project folder in File Explorer

Step 8:

Double click the new .sublime-project file to open it in sublime text (you may have to refresh File Explorer to see it)

Step 9:

Go to the main.cpp file in the src folder, and hit f7 to run it. Check that everything is fine by opening all of the folders and making sure you can see every file (not including .sublime-project and .sublime-workspace files, which should be hidden)

And, you've successfully changed the name of the .sublime-project and .sublime-workspace files!

Note: You may have to first open the .sublime-project file in Sublime Text and then refresh your file explorer to view the .sublime-workspace file, which should be the same name as your .sublime-project file.

## You may delete this file after copying the folder, but I would highly recommend keeping it incase you may need it for use.