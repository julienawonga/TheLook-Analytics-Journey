- Setup project (files and directories)
- init npm and install packages
    - npm init -y
    - npm install express mongoose cors nodemon

- create models
    - import mongoose
    - create schema
    - export schema


- create controllers and required method
    - import model
    - create crud with models and add following methods
        - add -> use Model.save()
        - get -> use Model.find()
        - update -> use Model.findByIdAndUpdate(req.params.id, req.body, {new: true})
        - delete -> use -> Model.findByIdAndDelete(req.params.id)
    - export methods

- create router and add router methods
    - import express and get router from express
    - import also controllers methods
    - create routes
        - router.get('/', method)
        - router.post('/', method)
        - router.put('/:id', method)
        - router.delete('/:id', method)
    - export router

