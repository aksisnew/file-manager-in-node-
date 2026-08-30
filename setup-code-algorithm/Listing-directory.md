To list the directory with node we will use async + await requests in render
so that there is no lag or halting of ui

# IMPORTANT SECURITY NOTE PLEASE ENSURE THE SECURITY OF THE ENVOIRNMENT AS WE ACCESSING SYSTEM FILE DIRECTORY.

1. we will send a request to node backend to list the directory , files, folders in a safe way without using/exposing core node apis in render process for security 
2. We will detect the file type, extension of the files , encoding of the files

here is an example implementation with built in node api for extension detection


``` 
const path = require('node:path);

const filePath = 'example.jpg';
const extension = path.extname(filePath); // returns '.jpg'
```

3. We will cache the directory in indexed db at render side , and add a watch for changes program which watches for changes in the directory and if there are changes with an api send a signal to the frontend to update the directory list cache, now the render process will send a api request back to the node backend to get the new directory list in async and await 