# Mongodb-Assignment-1


Step 1: Create the database  

    use codinggita

Step 2: Create the students collection      

    db.createCollection("students");

Step 3: Create the courses collection    

    db.createCollection("courses");
 
Step 4: Insert sample data into the students collection 
 

    db.students.insertMany([
    { 
    "name": "Jenil",
    "rollNumber": 101,
    "department": "Computer Science",
    "year": 2,
    "coursesEnrolled": ["CS101", "CS102"]
    },
    { 
    "name": "Mahir",
    "rollNumber": 102,
    "department": "Computer Science",
    "year": 2,
    "coursesEnrolled": ["CS101", "CS103"]
    },
    { 
    "name": "Arjun",
    "rollNumber": 103,
    "department": "Electrical Engineering",
    "year": 3,
    "coursesEnrolled": ["EE101", "EE102"]
    }
    ]);

Step 5: Insert sample data into the courses collection 

    db.courses.insertMany([
    { 
    "courseCode": "CS101", 
    "courseName": "Introduction to Programming", 
    "credits": 3, 
    "instructor": "Prof. Sharma" 
    },
    { 
    "courseCode": "CS102", 
    "courseName": "Data Structures", 
    "credits": 3, 
    "instructor": "Prof. Gupta" 
    },
    { 
    "courseCode": "CS103", 
    "courseName": "Algorithms", 
    "credits": 3, 
    "instructor": "Prof. Kapoor" 
    },
    { 
    "courseCode": "EE101", 
    "courseName": "Basic Electrical Engineering", 
    "credits": 4, 
    "instructor": "Prof. Verma" 
    },
    { 
    "courseCode": "EE102", 
    "courseName": "Circuit Theory", 
    "credits": 4, 
    "instructor": "Prof. Yadav" 
    }
    ]);

 Step 6: Query students based on department   

    db.students.find({ "department": "Computer Science" });

 Step 7: Query students based on year    
  
    db.students.find({ "year": 2 });

 Step 8: Query students by course enrollment   

    db.students.find({ "coursesEnrolled":  "CS101" });




 Step 9: Update a student’s courses

    db.students.updateOne(
    { "name": "Arjun" },
    { $push: { "coursesEnrolled": "CS102" } }
    );


Step 10: Update a course instructor If Prof. Gupta

     db.courses.updateOne(
    { "courseCode": "CS102" },
    { $set: { "instructor": "Prof. Mehta" } }
    );

   


 Step 11: Delete a student record 

     db.students.deleteOne({ "name": "Arjun" });


Step 2: Delete all students from a specific department

    db.students.deleteMany({ "department": "Electrical Engineering" });
   


