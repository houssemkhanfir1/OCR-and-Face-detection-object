
# OCR and Face detection project 

This project will take us through the process of processing images using the Python Library Image PIL, tesseract and open cv. 

1/ This is a project with minimal scaffolding. Expect to use the the discussion forums to gain insights! It’s not cheating to ask others for opinions or perspectives!.

2/ Be inquisitive, try out new things.

3/ Use the previous modules for insights into how to complete the functions! You'll have to combine Pillow, OpenCV, and Pytesseract.

4/ There are hints provided in Coursera, feel free to explore the hints if needed. Each hint provide progressively more details on how to solve the issue. This project is intended to be comprehensive and difficult if you do it without the hints.

# The Assignment
Take a ZIP file of images and process them, using a library built into python that you need to learn how to use. A ZIP file takes several different files and compresses them, thus saving space, into one single file. The files in the ZIP file we provide are newspaper images (like you saw in week 3). Your task is to write python code which allows one to search through the images looking for the occurrences of keywords and faces. E.g. if you search for "pizza" it will return a contact sheet of all of the faces which were located on the newspaper page which mentions "pizza". This will test your ability to learn a new (library), your ability to use OpenCV to detect faces, your ability to use tesseract to do optical character recognition, and your ability to use PIL to composite images together into contact sheets.

Each page of the newspapers is saved as a single PNG image in a file called images.zip. These newspapers are in english, and contain a variety of stories, advertisements and images. Note: This file is fairly large (~200 MB) and may take some time to work with, I would encourage you to use small_img.zip for testing.

## Notes
That big file can take some time to process - for me it took nearly ten minutes! Use the small one for testing.
## Hints

1/ To access the zip file logs, you must first use the Zipfile library to open the zip file and then browse the objects (logs) in the zip file using .infolist(). Try writing a simple routine to iterate through the zip file, printing the file name and using display().
Remember that the PIL.Image library can open files, and the .infolist() elements in the zip file appear to Python as if it were a file (this is called objects of type "file"). This allows you to convert PIL and CV imread formats using a physical file (or np.array object).

2/ You can spend a lot of time converting PIL.Image files to byte arrays, but you don't have to. Why not just store PIL.Image objects in a global data structure, perhaps a list or dictionary indexed by name? You can then process this data structure by adding  information such as text detected on pages or bounding boxes behind faces. Come to think of it, a list of dictionary objects, where each entry in the list would contain the PIL image, bounding boxes, and detected text on the page, would be a convenient way to store this data.

3/ Quick reminder: in Python, all character strings are lists of characters. Sort of (remember these are immutable lists - rather tuples!) But this means you can use the in keyword to find substrings very easily. So the following statement will return True if the substring is found: if "Christopher" in my_text.

4/ Creating the contact sheet can be a bit overwhelming. But you can resize images without having to worry about aspect ratio if you use the PIL.Image.thumbnail function. I used it to create the output images, maybe you should too! And watch the lecture on the contact sheet, you have to be careful not to stray from the end of the images when you create a row (or column).