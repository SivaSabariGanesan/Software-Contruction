::: mermaid

flowchart LR
  %% Actors
  User(["👤 User"])
  Trainer(["🧑‍🏫 Trainer"])
  Admin(["👨‍💼 Admin"])

  %% User Use Cases
  UC_Login((Register / Login))
  UC_Dashboard((View Dashboard))
  UC_Workout((Start Workout))
  UC_Exercise((Log Exercise))
  UC_Nutrition((View Nutrition Plan))
  UC_Meal((Log Meal))
  UC_Progress((Track Progress))
  UC_Profile((Update Profile))

  %% Trainer Use Cases
  UC_CreateWorkout((Create Workout Plan))
  UC_AssignWorkout((Assign Workout))
  UC_ViewProgress((View User Progress))

  %% Admin Use Cases
  UC_ManageUsers((Manage Users))
  UC_ManageWorkouts((Manage Workouts))
  UC_ManageNutrition((Manage Nutrition))

  %% Layout spacing
  subgraph USER_USE_CASES[ ]
    direction TB
    UC_Login
    UC_Dashboard
    UC_Workout
    UC_Exercise
    UC_Nutrition
    UC_Meal
    UC_Progress
    UC_Profile
  end

  subgraph TRAINER_USE_CASES[ ]
    direction TB
    UC_CreateWorkout
    UC_AssignWorkout
    UC_ViewProgress
  end

  subgraph ADMIN_USE_CASES[ ]
    direction TB
    UC_ManageUsers
    UC_ManageWorkouts
    UC_ManageNutrition
  end

  %% Connections to User
  User --> UC_Login
  User --> UC_Dashboard
  User --> UC_Workout
  User --> UC_Exercise
  User --> UC_Nutrition
  User --> UC_Meal
  User --> UC_Progress
  User --> UC_Profile

  %% Connections to Trainer
  Trainer --> UC_CreateWorkout
  Trainer --> UC_AssignWorkout
  Trainer --> UC_ViewProgress

  %% Connections to Admin
  Admin --> UC_ManageUsers
  Admin --> UC_ManageWorkouts
  Admin --> UC_ManageNutrition

  %% Use Case Relationships
  UC_Dashboard --> UC_Workout
  UC_Dashboard --> UC_Nutrition
  UC_Dashboard --> UC_Progress
  UC_Workout --> UC_Exercise
  UC_Nutrition --> UC_Meal


:::
