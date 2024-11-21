### mongoose:
* Mongodb DOM (document object model) library fro node.js.
* mongoose --> to interact with mongodb
* Schema --> The schema class is imported to define the structure, validation rules, and relationships for Mongodb documents.
* SuserId: {type: Schema.Types.ObjectId, ref: "User", required: true} --> Schema.Types.ObjectId --> will generate a mongodb Id (object id) to search from collections.
* ref: "User", by using this reference we can access User related documents
