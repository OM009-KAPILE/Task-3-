let marks = [45, 67, 89, 23, 99, 76];

// Using FOR loop
function findMaxFor(marks) {
  let max = marks[0];
  for (let i = 1; i < marks.length; i++) {
    if (marks[i] > max) {
      max = marks[i];
    }
  }
  return max;
}

// Using WHILE loop
function findMaxWhile(marks) {
  let i = 0;
  let max = marks[0];
  while (i < marks.length) {
    if (marks[i] > max) {
      max = marks[i];
    }
    i++;
  }
  return max;
}

// Using forEach loop
function findMaxForEach(marks) {
  let max = marks[0];
  marks.forEach(function(mark) {
    if (mark > max) {
      max = mark;
    }
  });
  return max;
}

console.log("Marks:", marks);
console.log("Highest (for):", findMaxFor(marks));
console.log("Highest (while):", findMaxWhile(marks));
console.log("Highest (forEach):", findMaxForEach(marks));



// Student data (nested object inside array)
let students = [
  {
    name: "Alice",
    marks: { math: 85, science: 92, english: 78 }
  },
  {
    name: "Bob",
    marks: { math: 58, science: 65, english: 60 }
  },
  {
    name: "Charlie",
    marks: { math: 95, science: 88, english: 91 }
  },
  {
    name: "David",
    marks: { math: 40, science: 55, english: 45 }
  }
];

let totals = students.map(student => {
  let total = student.marks.math + student.marks.science + student.marks.english;
  return { name: student.name, total: total };
});
console.log("\nTotal Marks (map):", totals);

let passedStudents = students.filter(student => {
  return student.marks.math >= 50 &&
         student.marks.science >= 50 &&
         student.marks.english >= 50;
});
console.log("\nPassed Students (filter):", passedStudents);

let subjectTotals = students.reduce((acc, student) => {
  acc.math += student.marks.math;
  acc.science += student.marks.science;
  acc.english += student.marks.english;
  return acc;
}, { math: 0, science: 0, english: 0 });

let averages = {
  math: subjectTotals.math / students.length,
  science: subjectTotals.science / students.length,
  english: subjectTotals.english / students.length
};
console.log("\nSubject Averages (reduce):", averages);

let report = {
  class: "10th Grade",
  students: totals,
  averages: averages,
  passed: passedStudents.map(s => s.name)
};

console.log("\nFinal Report (nested object):", report);
