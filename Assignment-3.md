1. Additional Questions on CRUD Operations:
   
   fisrt create a file
     
         use assign

    after add collection of students

         db.createCollection("student")    

   Insert new students into the "students" collection with random data
        
        db.students.insertMany([
        {
        name: "Jenil",
        rollNumber: "CS1001",
        department: "CSE",
        year: 2,
        coursesEnrolled: ["CS101", "MATH202", "PHY101"],
        },
        {
        name: "Mahir",
        rollNumber: "CS1002",
        department: "IT",
        year: 1,
        coursesEnrolled: ["CS101", "MATH101"],
        },
        {
        name: "Arjun",
        rollNumber: "CS1003",
        department: "CSE",
        year: 3,
        coursesEnrolled: ["CS301", "MATH303"],
        },
        {
        name: "Yashvi",
        rollNumber: "CS1004",
        department: "ECE",
        year: 2,
        coursesEnrolled: ["ECE201", "MATH202"],
        },
        ]);


Update the department of a student based on their roll number.

        db.students.updateOne(
        {"rollNumber":"CS1004"},
        {$set:{department:"IT"}})


Remove all students who have enrolled in less than 3 courses.

        db.students.deleteMany(
        {$expr:{$lt: [{$size:"$coursesEnrolled"},3]}})

2. Aggregation Exercise: 

Use aggregation to find the department with the most number of students.

       db.students.aggregate([
       { $group: { _id: "$department", totalStudents: { $sum: 1 } } },
       ]);

3. Advanced Querying Exercise:

Query students who have enrolled in a specific set of courses (e.g., CS101 and MATH101).
    
     <!-- using all  -->

       db.students.findOne({
       coursesEnrolled: { $all: ["CS101", "MATH202"] }
       });


       <!-- using and -->
      
       db.students.find({
       $and: [
       { coursesEnrolled: "CS101" },
       { coursesEnrolled: "MATH202" }
       ]
       });


4. Indexing and Performance:

Experiment with creating indexes on various fields like department, year, etc., and measure the query performance using explain().


        
    
  