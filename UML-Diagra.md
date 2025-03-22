+------------------+
|      User                                            |
+------------------+
| - userId: int   |
| - name: string  |
| - email: string |
| - age: int      |
| - gender: string|
| - weight: float |
| - height: float |
+------------------+
| + register()    |
| + login()       |
| + updateProfile() |
+------------------+
        |
        | 1
        | *
+------------------+
|    Subscription  |
+------------------+
| - subscriptionId: int |
| - userId: int         |
| - planType: string    |
| - startDate: date     |
| - endDate: date       |
| - status: string      |
+------------------+
| + activatePlan()     |
| + cancelPlan()       |
+------------------+
        |
        | 1
        | *
+------------------+
|     Trainer     |
+------------------+
| - trainerId: int|
| - name: string  |
| - specialization: string |
| - experience: int |
| - contactInfo: string |
+------------------+
| + assignWorkout() |
| + assignDietPlan() |
+------------------+
        |
        | 1
        | *
+------------------+
|    Workout      |
+------------------+
| - workoutId: int|
| - userId: int   |
| - trainerId: int|
| - type: string  |
| - duration: int |
| - caloriesBurned: float |
+------------------+
| + startWorkout() |
| + trackProgress() |
+------------------+
        |
        | 1
        | *
+------------------+
|    Diet Plan    |
+------------------+
| - dietId: int   |
| - userId: int   |
| - trainerId: int|
| - mealPlan: string |
| - caloriesIntake: float |
+------------------+
| + updateDiet() |
+------------------+
