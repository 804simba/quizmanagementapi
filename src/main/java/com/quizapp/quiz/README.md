The design of the models aims to represent the entities and their relationships in a way that aligns with the requirements of a quiz application. Here are the reasons behind the design:

1. **User Entity:**
    - Represents individual users participating in the system.
    - Includes essential user information such as `username` and `email`.
    - Uses a generated unique identifier (`userId`).

2. **Quiz Entity:**
    - Represents quizzes within the application.
    - Contains details like `title`, `description`, and `difficultyLevel`.
    - Utilizes a One-to-Many relationship with both `Question` and `QuizAttempt`, allowing one quiz to have multiple associated questions and attempts.
    - Uses a generated unique identifier (`quizId`).

3. **Question Entity:**
    - Represents individual questions within a quiz.
    - Captures details like `questionText`, `questionType`, and `correctAnswer`.
    - Utilizes a Many-to-One relationship with the `Quiz` entity, indicating that each question belongs to a specific quiz.
    - Has a generated unique identifier (`questionId`).

4. **QuizAttempt Entity:**
    - Represents a user's attempt at a specific quiz.
    - Includes a reference to the `User` and `Quiz` entities through Many-to-One relationships, indicating the user and quiz associated with the attempt.
    - Stores the user's `submittedAnswers` and the resulting `score`.
    - Has a generated unique identifier (`attemptId`).

This model design allows for efficient representation of users, quizzes, questions, and quiz attempts, supporting the quiz application's functionality such as tracking user attempts, storing quiz content, and calculating scores. The use of JPA annotations (`@Entity`, `@ManyToOne`, `@OneToMany`, etc.) ensures that the relationships are mapped correctly in the underlying database.


````bash
{
"questionText": "What is the capital of France?",
"options": ["Paris", "Berlin", "Madrid", "Rome"],
"correctAnswer": "Paris",
"difficultyLevel": "MEDIUM",
"subjectCategory": "Geography"
}
