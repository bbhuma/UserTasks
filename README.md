# UserTasks
Tasks assigned to different Users, @ManyToOne tasks to user entitiy

Spring boot project with @ManyToOne Detailed discussion DTO based backend api development  https://chat.openai.com/share/3021e959-b1a4-49c8-a5e7-dfe004b705a5 

Write SQL queries - 
USE usertasks;

SELECT * from task where user_id=1;----> this is more appropriate for /api/users/1/tasks
![image](https://github.com/bbhuma/User-Tasks-Project/assets/25493400/24330de3-f19a-4ae7-b65a-c1c68ee62f10)


SELECT * FROM task INNER JOIN user ON task.user_id = user.id where user.id=1;
![Uploading image.png…]()


SELECT * FROM task WHERE user_id = 1 AND id = 9;

User controller for handling User end point like - /api/users/{user_id}
Task controller for handling task endpoints like - /api/users/{user_id}/tasks/{task_id} 
- All the end points in Task controller takes and  gives you Task Object or TaskDTO object.
- Task Class has User reference, so always find userById then assign the User object to the Task Object.
- set id, taskname from the i/p taskDTO object.
- 
Can you create two contorllers called userController and Task controller in a one to many relationship between User and Tasks. with feilds as id,nam,email on User and id, name on tasks. The follwing end points should be implemented 
POST /api/users - Create new User
GET /api/users - Get all Users
PUT /api/users/{userId} - Update an existing User details
DELETE /api/users/{userId} - Delete an User
POST /api/login - Login as existing User
POST /api/users/{userId}/tasks - Assign new tasks to existing user
GET /api/users/{userId}/tasks - Get all tasks of a user
GET /api/users/{userId}/tasks/{taskId} - Get details of specific task_id of a specific user_id
PUT /api/users/{userId}/tasks/{taskId} - Update tasks of a user
DELETE /api/users/{userId}/tasks/{taskId} - Delete tasks of a user
DELETE /api/users/{userId}/tasks - Delete all tasks of a user
TaskController:

GET /api/tasks/{taskId} - Get details of specific task
GET /api/users/{userId}/tasks - Get tasks of a particular user with id
So, in total, you would need two controllers, one for User related endpoints and one for Task related endpoints.

<img width="878" alt="image" src="https://github.com/bbhuma/User-Tasks-Project/assets/25493400/9f9457b2-7630-41d7-ba1e-41a2144117af">

Need of DTO class, we dont need to send user info again if we used task.java so we use TaskDTO.java instaed of task.java 
<img width="866" alt="image" src="https://github.com/bbhuma/User-Tasks-Project/assets/25493400/0b34cf6a-1921-497c-9373-7108719ba941">

