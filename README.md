# Blog System - Spring Boot Application

A modern blog platform built with Spring Boot, PostgreSQL, and Thymeleaf. This application demonstrates CRUD operations, user authentication, role-based access control, and a responsive web interface.

## Features

### 🔐 Authentication & Authorization
- User registration and login
- Role-based access control (ADMIN and USER roles)
- Secure password encryption with BCrypt
- Spring Security integration

### 📝 Blog Management
- **Create**: Write and publish new blog posts
- **Read**: View all blogs and individual blog posts
- **Update**: Edit existing blog posts (authors and admins only)
- **Delete**: Remove blog posts (authors and admins only)
- **Search**: Find blogs by keywords in title or content

### 🎨 User Interface
- Responsive design with Bootstrap 5
- Modern and clean UI with Font Awesome icons
- 6+ HTML pages with Thymeleaf templating
- User-friendly navigation and forms

### 🗄️ Database
- PostgreSQL database integration
- JPA/Hibernate for ORM
- Automatic table creation and sample data initialization

## Technology Stack

- **Backend**: Spring Boot 3.5.3, Java 24
- **Database**: PostgreSQL
- **ORM**: Spring Data JPA with Hibernate
- **Security**: Spring Security
- **Frontend**: Thymeleaf, Bootstrap 5, Font Awesome
- **Build Tool**: Maven
- **Other**: Lombok, Validation

## Prerequisites

Before running this application, make sure you have:

1. **Java 24** or higher installed
2. **PostgreSQL** database server running
3. **Maven** installed (optional, can use Maven wrapper)

## Database Setup

1. Create a PostgreSQL database named `blog_system`
2. Update the database configuration in `application.properties` if needed:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/blog_system
spring.datasource.username=postgres
spring.datasource.password=password
```

## Running the Application

### Option 1: Using Maven Wrapper (Recommended)
```bash
# Navigate to the project directory
cd Blog_System/Blog_System

# Run the application
./mvnw spring-boot:run
```

### Option 2: Using Maven
```bash
# Navigate to the project directory
cd Blog_System/Blog_System

# Run the application
mvn spring-boot:run
```

### Option 3: Using IDE
1. Open the project in your IDE (IntelliJ IDEA, Eclipse, etc.)
2. Run the `BlogSystemApplication` class

## Accessing the Application

Once the application is running, you can access it at:
- **Homepage**: http://localhost:8080
- **Blogs**: http://localhost:8080/blogs
- **Login**: http://localhost:8080/login
- **Register**: http://localhost:8080/register

## Default Users

The application comes with pre-configured users for testing:

### Admin User
- **Username**: admin
- **Password**: admin123
- **Role**: ROLE_ADMIN
- **Capabilities**: Full access to all features

### Regular Users
- **Username**: john
- **Password**: password123
- **Role**: ROLE_USER
- **Capabilities**: Create, read, update, delete own blogs

- **Username**: jane
- **Password**: password123
- **Role**: ROLE_USER
- **Capabilities**: Create, read, update, delete own blogs

## Project Structure

```
src/main/java/com/Blog_System/Blog_System/
├── BlogSystemApplication.java          # Main application class
├── config/
│   ├── SecurityConfig.java            # Spring Security configuration
│   └── DataInitializer.java           # Sample data initialization
├── controller/
│   ├── AuthController.java            # Authentication endpoints
│   ├── BlogController.java            # Blog CRUD endpoints
│   └── HomeController.java            # Home and dashboard endpoints
├── dto/
│   ├── BlogDto.java                   # Blog data transfer object
│   └── UserRegistrationDto.java       # User registration DTO
├── entity/
│   ├── Blog.java                      # Blog entity
│   ├── Role.java                      # Role enum
│   └── User.java                      # User entity
├── repository/
│   ├── BlogRepository.java            # Blog data access
│   └── UserRepository.java            # User data access
└── service/
    ├── BlogService.java               # Blog business logic
    └── UserService.java               # User business logic
```

## HTML Pages

The application includes 6+ HTML pages:

1. **Home Page** (`home.html`) - Welcome page with recent blogs
2. **Login Page** (`auth/login.html`) - User authentication
3. **Registration Page** (`auth/register.html`) - User registration
4. **Blog List Page** (`blog/list.html`) - Display all blogs
5. **Blog View Page** (`blog/view.html`) - Individual blog post
6. **Blog Create Page** (`blog/create.html`) - Create new blog
7. **Blog Edit Page** (`blog/edit.html`) - Edit existing blog
8. **Search Results Page** (`blog/search.html`) - Search functionality
9. **Dashboard Page** (`dashboard.html`) - User dashboard

## Role-Based Access Control

### ADMIN Role
- Can perform all operations (Create, Read, Update, Delete)
- Can manage all blogs (own and others')
- Full access to the system

### USER Role
- Can create, read, update, and delete their own blogs
- Can read and search all blogs
- Cannot modify other users' blogs

## API Endpoints

### Public Endpoints
- `GET /` - Home page
- `GET /blogs` - List all blogs
- `GET /blogs/{id}` - View specific blog
- `GET /blogs/search` - Search blogs
- `GET /login` - Login page
- `GET /register` - Registration page

### Authenticated Endpoints
- `GET /dashboard` - User dashboard
- `GET /blogs/my-blogs` - User's own blogs
- `GET /blogs/create` - Create blog form
- `POST /blogs/create` - Create new blog
- `GET /blogs/{id}/edit` - Edit blog form
- `POST /blogs/{id}/edit` - Update blog
- `POST /blogs/{id}/delete` - Delete blog

## Security Features

- Password encryption with BCrypt
- CSRF protection
- Session management
- Role-based authorization
- Input validation and sanitization

## Customization

### Adding New Features
1. Create new entities in the `entity` package
2. Add corresponding repositories in the `repository` package
3. Implement business logic in the `service` package
4. Create controllers in the `controller` package
5. Add Thymeleaf templates in `resources/templates`

### Styling
- Bootstrap 5 classes are used for styling
- Custom CSS can be added to the `<style>` sections in HTML files
- Font Awesome icons are used throughout the application

## Troubleshooting

### Common Issues

1. **Database Connection Error**
   - Ensure PostgreSQL is running
   - Check database credentials in `application.properties`
   - Verify database `blog_system` exists

2. **Port Already in Use**
   - Change the port in `application.properties`: `server.port=8081`

3. **Java Version Issues**
   - Ensure Java 24+ is installed and set as JAVA_HOME

### Logs
- Application logs are available in the console
- Debug logs can be enabled by setting `logging.level.com.Blog_System=DEBUG`

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is created for educational purposes as part of a Spring Boot assignment.

## Support

For any issues or questions, please check the troubleshooting section above or create an issue in the repository. 