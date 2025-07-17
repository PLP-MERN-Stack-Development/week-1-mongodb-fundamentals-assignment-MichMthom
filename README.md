db.books.insertOne({
  title: "New Book",
  author: "Author Name",
  publicationYear: 2023
});
db.books.find({ author: "Author Name" });db.books.updateOne(
  { title: "New Book" },
  { $set: { publicationYear: 2024 } }
);
db.books.deleteOne({ title: "New Book" });
db.books.find({ publicationYear: { $gt: 2020 } });
db.books.find({}, { title: 1, author: 1 });
db.books.find().sort({ publicationYear: -1 });
db.books.aggregate([
  {
    $group: {
      _id: "$author",
      count: { $sum: 1 }
    }
  },
  {
    $sort: { count: -1 }
  }
]);
db.books.createIndex({ author: 1 });
