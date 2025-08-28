// Student data (array of objects)
const students = [
  { id: 1, name: "Om", marks: 85 },
  { id: 2, name: "Aarav", marks: 92 },
  { id: 3, name: "Riya", marks: 45 },
  { id: 4, name: "Neha", marks: 76 },
  { id: 5, name: "Karan", marks: 32 }
];

// 1. Get all student names using map
const studentNames = students.map(student => student.name);
console.log("All Students:", studentNames);

// 2. Filter students who passed (marks >= 40)
const passedStudents = students.filter(student => student.marks >= 40);
console.log("Passed Students:", passedStudents);

// 3. Find average marks using reduce
const totalMarks = students.reduce((sum, student) => sum + student.marks, 0);
const avgMarks = totalMarks / students.length;
console.log("Average Marks:", avgMarks);

// 4. Find topper (highest marks)
const topper = students.reduce((max, student) => student.marks > max.marks ? student : max, students[0]);
console.log("Topper:", topper);
