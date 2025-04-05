::: mermaid
sequenceDiagram
    participant User
    participant App
    participant AuthService
    participant WorkoutService
    participant ProgressTracker

    User ->> App: Open App
    App ->> AuthService: Check login status
    AuthService -->> App: Return login status
    App ->> User: Show login screen (if not logged in)
    User ->> App: Enter credentials
    App ->> AuthService: Validate credentials
    AuthService -->> App: Authentication success
    App ->> User: Show dashboard

    User ->> App: Select workout plan
    App ->> WorkoutService: Fetch workout details
    WorkoutService -->> App: Return workout details
    App ->> User: Show workout routine

    User ->> App: Start workout
    loop For each exercise
        User ->> App: Log exercise (sets, reps, duration)
        App ->> ProgressTracker: Save exercise data
    end

    App ->> ProgressTracker: Calculate progress update
    ProgressTracker -->> App: Return updated stats
    App ->> User: Show progress summary

    User ->> App: Logout
    App ->> AuthService: End session

:::
