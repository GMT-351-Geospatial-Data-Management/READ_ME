# Overview
### Backend
- PostgreSQL must be installed and running. Windows 11 64bit PostgreSQL 15 was used for this project.
- Postman is an API (Application Programming Interface) development platform for testing and modifying APIs.
### Frontend
- React deals with a user input field and displaying the value in a table. The user can edit and delete inputs.
- Javascript XLM (JSX) and HTML: At the heart of a website are HTML documents. Your web browser reads these documents and displays them as web pages on the screen of your computer or other electronic devices you use. During this process, browsers create a structure called Document Oriented Model (DOM) about how pages are arranged. Updating the DOM using JSX brings an incredible website performance boost and development efficiency. (see JavaScript XML (JSX) , React Fragments )

### Technologies - Backend
- [PostgreSQL v15](https://www.postgresql.org/) - to manage database
- [Express.js middleware v4](https://expressjs.com/)- to build RESTful APIs with Node.js
- [Node.js v18](https://nodejs.org/en/)- to create the server side
- [Postman API](https://www.postman.com/) to simulate frontend

### Technologies - Frontend
- [React framework v18](https://reactjs.org/) - to create user interfaces
- [ Bootstrap v5](https://getbootstrap.com/) - to improve web page designs

### Pre-Setup
- All necessary components must be downloaded.
- should have a basic knowledge of Javascript and React.
- This will also help you if you have knowledge of how the Restful API (CRUD app) works.

### Overview Diagram
<img width="603" alt="image" src="https://user-images.githubusercontent.com/119863892/212556523-96fe373a-679c-4040-a199-5c3319b511e5.png">

### Build Our Server
- "server" folder is created. (see server)
- ```npm init```
- dependencies are downloaded. ```npm i express pg cors```
  * Express is a Node.js based web application server framework.
  * ```pg``` is a non-blocking PostgreSQL client for Node.js.
  * Cors allows the web application to receive HTTP requests from different sources.
- "index.js" created. (see index.js)
- "databased.sql" created. (see database)
  * Contains source codes of database and tables
- In terminal under server folder thanks to commands ```cd server```  ```touch index.js```  and ```node index``` server starts at ```http://localhost:5000/```
### Connect Our Database and Server
- The PostgreSQL library is linked with the "db.js" script file. (see db.js)
  * In this file, database information is defined.
- Routes sections are written in "index.js" and CRUD processing capability is gained with query commands - POST, GET, PUT, DELETE etc.
### Set Up the Client Side
- "Client" folder is created. (see (bkz. Client)
- Input, List and Edit components are created using Fragment, useState structures.
  * Fragments allow you to group a list of child elements without adding extra nodes to the Dom.
  * The useState function lets you use state and other React features without creating any classes.
- It should be imported into "App.js". (see (bkz. App.js)
- The site is run at the address of ``` http://localhost:3000/``` with ```cd client ``` ```npm start ``` under  the client folder in the terminal.


### Code Examples - Backend
``` python
//ROUTES//

//Create a Club
app.post("/clubss", async(req,res) => {
    try {
        const { name } = req.body;
        const newClub = await pool.query(
            "INSERT INTO clubs (name) VALUES($1) RETURNING *",
        [name]
        );
        res.json(newClub.rows[0]);
    } catch (err) {
        console.error(err.message);
    }
});

```
### Code Examples - Frontend
``` python
const InputClub = () => {

    const [name, setName] = useState("")
    const onSubmitForm = async(e) => {
        e.preventDefault();
        try {
            const body = {name};
            const response =await fetch("http://localhost:5000/clubss", {
                method: "POST",
                headers: { "Content-Type": "application/json"},
                body: JSON.stringify(body)
            });
            window.location ="/";
            
        } catch (err) {
            console.error(err.message)
            
        }
    }
```

## Screenshots
- Database
<img width="585" alt="image" src="https://user-images.githubusercontent.com/119863892/212557802-489c1cb1-dbed-4696-a5bb-41b58e9011e8.png">

- Postman testing
<img width="589" alt="image" src="https://user-images.githubusercontent.com/119863892/212558182-dc525e14-2b4f-4518-8c1a-9a71d45299d8.png">

- Console Log 
<img width="563" alt="image" src="https://user-images.githubusercontent.com/119863892/212558531-dae75b52-2c7a-44af-baaf-97272b33afa3.png">

### General Tools / References
- [PERN Stack Course - Postgres, Express, React, and Node](https://youtu.be/ldYcgPKEZC8)
- [React documentation](https://reactjs.org/docs/getting-started.html)
- [JS-beautify for VS Code](https://marketplace.visualstudio.com/items?itemName=HookyQR.beautify)
- [ES7+ React/Redux/React-Native snippets](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets)
- [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [Markdown Preview Enhanced](https://marketplace.visualstudio.com/items?itemName=shd101wyy.markdown-preview-enhanced)

### Contact
- [Asude Nurun Akgümüş](https://github.com/nrnakg) -[Gmail](asudenrnakgumus@gmail.com)
- [Sude Yaprak Köse](https://github.com/sudeyaprak) - [Gmail](sudeyapraksyks@gmail.com)
- [Fatma Burcu Arslan](https://github.com/Burcu348) - [Gmail](burcuarslan@hacettepe.edu.tr)






