Task 1: Add multiple students

 first create a new file

       use task;

after create students and courses collection

    db.createCollection("students"); 

    db.createCollection("coueses");  

and a multiple student data

    db.students.insertMany([
    { 
    "name": "Jenil",
    "rollNumber": 101,
    "department": "Computer Science",
    "year": 2,
    "subjectsEnrolled": ["React", "NodeJS", "MongoDB"]
    },
    { 
    "name": "Mahir",
    "rollNumber": 102,
    "department": "Computer Science",
    "year": 2,
    "subjectsEnrolled": ["React", "NodeJS"]
    },
    { 
    "name": "Arjun",
    "rollNumber": 103,
    "department": "Electrical Engineering",
    "year": 3,
    "subjectsEnrolled": ["Circuit Theory", "Electrical Machines"]
    }, 
    { 
    "name": "Shivam",
    "rollNumber": 104,
    "department": "Computer Science Engineering",
    "year": 1,
    "subjectsEnrolled": ["React", "HTML", "MongoDB"]
    },
    { 
    "name": "Mayur",
    "rollNumber": 105,
    "department": "Computer Science",
    "year": 2,
    "subjectsEnrolled": ["React", "NodeJS", "MongoDB"]
    },


    ]);       


Task 2: Add multiple subjects

   db.subjects.insertMany([
    { 
    "subjectName": "React",
    "topics": [
      "JSX", 
      "Components", 
      "State", 
      "Props", 
      "Hooks"
    ]
    },
    { 
    "subjectName": "NodeJS", 
    "topics": [
      "Modules", 
      "Express", 
      "File System", 
      "Asynchronous Programming"
    ]
    },
    { 
    "subjectName": "MongoDB", 
    "topics": [
      "Database Design", 
      "CRUD Operations", 
      "Aggregation", 
      "Indexes"
    ]
    },
    { 
    "subjectName": "c language", 
    "topics": [
      "Arrays", 
      "String", 
     
    ]
    },
    { 
    "subjectName": "MongoDB", 
    "topics": [
      "Database Design", 
      "CRUD Operations", 
      "Aggregation", 
      "Indexes"
    ]
    }
    ]);

Task 3: Query students based on subject enrollment

    db.students.find({ "subjectsEnrolled": "NodeJS" });

Task 4: Add a new topic to a subject

    db.subjects.updateMany(
    {"subjectName":"NodeJS"},
    {$set:{"marks":"150"}})    

Task 5: Query subjects with multiple topics




Task 6: Update student enrollment

    db.students.updateOne(
    { "name": "Jenil" },
    { $push: { "subjectsEnrolled": ["React Native"] } }
    );

Task 7: Query all students    
   
    db.students.find({}, { name: 1, subjectsEnrolled: 1, _id: 0 }).forEach(student => { print(`Name: ${student.name}`);
    print(`Enrolled Subjects: ${student.subjectsEnrolled ? student.subjectsEnrolled.join(", ") : "None"}`);
    });

Task 8: Update multiple students' year

    db.students.updateMany(
    {"department":"Computer Science"},
    {$set:{"year":"3"}})  

Task 9: Add new topics to multiple subjects
    
    db.subjects.updateOne(
    {"name":"React"},
    {$push:{"topics":"Hooks"}}) 


    db.subjects.updateOne(
    {"name":"React"},
    {$push:{"topics":"Hooks"}}) 


    db.subjects.updateOne(
    {"name":"React"},
    {$push:{"topics":"Hooks"}}) 


Task 10: Remove a topic from a subject
   
    db.subjects.deleteOne(
    {"topics":"Express"})

Task 11: Query all students in a specific year
    
    db.students.find(
    {"year":{$in:[2,3]}})    

Task 12: Delete a student by roll number

    db.students.deleteOne(
    {"rollNumber":103})   

Task 13: Delete all students from a department

    db.students.deleteOne(
    {"department":"Computer Science Engineering"})

Task 14: Retrieve all topics for a subject

    db.subjects.findOne(
    {"subjectsName":"MognoDB"})

Task 15: Count the number of subjects in which a student is enrolled  
  