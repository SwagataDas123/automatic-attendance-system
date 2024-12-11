## PROBLEM DEFINITION
The Automated Attendance System using Face Detection technology is far better than the age old manual system of taking attendance. The manual attendance taking procedure is a tedious job. It takes a lot of time and effort to take attendance of all the individuals present in an organization. The manual attendance system is subject to numerous discrepancies. One might act as a proxy for the other individual which might be reasons of mistrust among the organization. In case of Automated system, this problem will not hold true. This is because the individual have to be present in the organization for him/her to scan their face through the webcam device and then only the attendance sheet will be updated. Moreover, manual attendance system is not viable for large organizations. There can be several anomalies in the manual attendance system. People having same names can not be distinguished uniquely in manual system which might lead to several errors in data handling. When we use automated system, since the face of the individual is detected, so, these errors can be minimized.

## ARCHITECTURE
The project uses OpenCV and the face_recognition library to detect faces in webcam footage and compare them to a pre-existing set of known faces.
The known faces are stored in the "ImageAttendance" folder as images, with each image representing an unique person.
The script reads the images from the "ImageAttendance" folder, and then uses the face_recognition library to find the encodings for each face. 
Once the encodings are obtained, the script starts capturing images from the webcam in a while loop. 
For each frame captured, the script uses the face_recognition library to detect faces in the frame and find their encodings. 
It then compares the detected faces' encodings to the known faces' encodings, and if a match is found, it will display the name of the matched person on the webcam footage and also mark attendance in "Attendance.xlsx" file 
The script will continue to run in this loop until the user interrupts it. 
It also uses openpyxl library to read and write data to an excel file "Attendance.xlsx". 
Overall, this project uses a simple architecture that is based on the following steps: 
Preprocessing the known faces Capturing webcam footage 
Detecting and encoding faces in the webcam footage 
Comparing the detected faces to the known faces 
Displaying the name of the matched person and marking attendance in an excel file if a match is found.

## DETAILED WORKING
The Automated Attendance System using Face Recognition is implemented using Python. We are usingface_recognition library to perform the face recognition needed in our system. To use the face_recognition library, we need to install dlib first then continue to install the face_recognition library.
We are importing the different libraries needed in our system. The OpenCV library is imported using cv2. NumPy is basically a Python library used to work with arrays and is imported for creating different arrays needed in our algorithm. It stands for Numerical Python. The OS module in Python is used to create a link between the operating system and user. It performs different OS based tasks. The datetime module imported is used to handle date and time in our program. By importing this module, users can add current date and time in their program. PIL stands for Python Imaging Library which gives the python interpreter all the image editing capabilities. The ImageGrab module of PIL is used to copy the contents of the screen or even the clipboard to PIL image memory.
The openpyxl module is used to read from and write in Excel files. It allows Python programs to read and modify Excel files.To create a new Excel file using openpyxl library, we need to import the library and then create a workbook object.
This code is using the OpenCV library to read a directory of images located at the specified path, "ImageAttendance", and appends each image and its corresponding class name (the file name without the file extension) to separate lists, "images" and "classNames", respectively. The os.listdir() function is used to get a list of all files in the directory, and the os.path.splitext() function is used to get the file name without the file extension. It then prints out the class names.
The face_recognition library only supports images in BGR (Blue, Green, Red) format. Therefore, we are converting our images into BGR format using cvtColor(img, cv2.COLOR_BGR2RGB). The face_recognition.face_encodings(img)[0] function returns encodings of a particular image. 
The markAttendance() method is used to update the “Attendance.xlsx” file. If the name of the person is already in the spreadsheet, the sheet will not be updated. The datetime module is used to update the date and time in our program. If the name is not in the spreadsheet, the sheet will be updated with the proper time when the webcam detects a new person.
The face encoding is getting complete here. Encoding refers to the process of creating a numerical representation of a face, known as a face encoding. The face_recognition library uses a deep learning model to analyse the unique features of a face, such as the distance between the eyes, nose, and mouth, and creates a numerical representation of those features, known as a face encoding. This encoding can then be used to compare against a known set of face encodings to determine if a face in a new image matches one of the known faces. The cv2.VideoCapture(0) is used to return the video recorded by the first webcam of our computer or system.
The script captures video frames from the webcam using the cap.read() function and processes each frame to detect and recognize faces in the frame. The script then uses the face_recognition library to compare the detected faces to a pre-existing list of known faces, and if a match is found, the script will mark attendance for the recognized individual and display the individual's name on the webcam video feed. The script also saves the attendance information in an excel file "Attendance.xlsx"
The cv2.imshow(‘Webcam’, img)  is used to display an image in a window. The cv2.waitKey() function allows us to wait for a specific time in milliseconds until any button from the keyboard is being pressed.
At last, we are saving all the necessary changes in our ‘Attendance.xlsx” file.

Once, we compile and run this code, webcam will open and detect the known face and update the attendance file as shown in the following pictures.







