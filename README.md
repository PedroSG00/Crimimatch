# Crimimatch
Developed by Raquel Tejada and Pedro Suárez

Tabla de Endpoints:

| HTTP METHOD | URI PATH | DESCRIPTION | JSON |
| --- | --- | --- | --- |
| GET | / | Index page |  |
| GET | /news/create | News create form |  |
| POST | /news/create | News create form handler |  |
| GET | /news/list | News list render |  |
| GET | /news/{id} | News details render |  |
| GET | /news/{id}/edit | Edit news form render |  |
| POST | /news/{id}/edit | Edit news form handler |  |
| POST | /news/{id}/delete | Delete new | |
| GET | /api/news | News list | ✔️|
| GET | /api/news/{id} | News details | ✔️ |
| GET | /news/{id}/create-comment | New comment form |  |
| POST | /news/{id}/create-comment | New comment handler |  |
| GET | /news/{id}/edit-comment | Edit comment form | |
| POST | /news/{id}/edit-comment | Edit comment handler | |
| POST | /news/{id}/delete-comment | Delete comment form  |  |
| GET | /wanted/api | Most wanted list render | |
| GET | /wanted/api/{id} | Criminal details render | |
| GET | /match | Get criminal match form render |  |
| POST | /match | Criminal match form handler |  |


Models:
  User, News, Comments.
  
  User: {
  
    email: {
    type: String
    required: true
    unique: true
    }
    
    profileImage: {
    type: String
    }

    username: {
    type: String
    required: true
    }

    password: {
    type: String,
    required: true
    }
    
    role: {
     type: String,
     Enum: ['USER', 'MODERATOR', 'ADMIN'],
     default: 'USER'
    }
    
    {
     
     timestamps: true
     
     }

}

  News: {
  
    header: {
    type: String,
    required: true,
    }
    
    image: {
    type: String,
    rewquired: true
    }
    
    body: {
    type: String,
    required: true
    }
    
    link: {
    type: String,    
    }
    
    comments: {
     type: mongoose.Types.ObjectId,
     ref: 'Comments'
     }
     
     {
     
     timestamps: true
     
     }
    
    
   }
    
   Comments: {
    
    author: {
    type: mongoose.Types.ObjectId,
    ref: User
    }
    
    text: {
    
    type: String
    required: true
    
    }
    
    {
     
    timestamps: true
     
    }
    
}
    
  
  
  
  
  








