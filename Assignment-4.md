Task 1: Add more students to the students collection

   db.students.insertMany([
    {
        name: "Aarav Mehta",
        rollNumber: "STU1005",
        courses: ["Mathematics", "Physics", "Chemistry"]
    },
    {
        name: "Ishani Kapoor",
        rollNumber: "STU1006",
        courses: ["Biology", "English", "Environmental Science"]
    },
    {
        name: "Rohan Gupta",
        rollNumber: "STU1007",
        courses: ["Computer Science", "Mathematics", "Statistics"]
    },
    {
        name: "Meera Sharma",
        rollNumber: "STU1008",
        courses: ["Economics", "History", "Political Science"]
    },
    {
        name: "Kabir Nair",
        rollNumber: "STU1009",
        courses: ["Physics", "Astronomy", "Advanced Calculus"]
    }
]);




Task 2: Insert a new course into the courses collection

    db.courses.insertMany([
    {
        courseCode: "CS202",
        name: "Data Structures",
        credits: 3,
        instructor: "Prof. Krishna"
    },
    {
        courseCode: "CS203",
        name: "Algorithms",
        credits: 4,
        instructor: "Prof. Meera Patel"
    },
    {
        courseCode: "CS204",
        name: "Operating Systems",
        credits: 3,
        instructor: "Prof. Rajesh Kumar"
    },
    {
        courseCode: "CS205",
        name: "Database Management Systems",
        credits: 3,
        instructor: "Prof. Priya Sharma"
    },
    {
        courseCode: "CS206",
        name: "Computer Networks",
        credits: 4,
        instructor: "Prof. Anil Verma"
    }
]);

Task 3: Fetch a specific student's record by roll number

    db.students.findOne(
    {"rollNumber":STU1005})

Task 4: Query all students who are enrolled in a particular course

    db.courses.find(
    {"courseCode":"CS206"})

Task 5: Update a student's courses

    db.students.updateOne(
    {"rollNumber":"STU1009"},
    {$push:{"courses":"CS202"}})

Task 6: Remove a course from a student's courses list

    db.students.updateOne(
    {"name":"Kabir Nair"},
    {$pull:{"courses":"CS202"}})

Task 7: Find all courses with 3 credits

    db.courses.find(
    {"credits":3})  

Task 8: Find students who have enrolled in more than 2 courses

    db.students.find({
    $expr: { $gt: [{ $size: "$courses" }, 2] } 
    });

Task 9: Use the $in operator to find students enrolled in multiple courses

    db.students.find(
    {"courses":{$in:["Physics" , "Astronomy"]}})  

Task 10: Fetch all students from a specific department (e.g., CSE)

    db.students.find(
    {"courses":"Physics"})

Task 11: Query students who are in their 3rd year

    

     
    
