def main():
    print("Welcome to the Calorie Counting Program!")
    
    # Dictionary to store food items and their calorie content
    food_log = {}
    
    while True:
        print("\nMenu:")
        print("1. Add food and calorie count")
        print("2. View total calories")
        print("3. View all food items")
        print("4. Exit")
        
        choice = input("Enter your choice (1-4): ")
        
        if choice == '1':
            add_food(food_log)
        elif choice == '2':
            view_total_calories(food_log)
        elif choice == '3':
            view_all_food_items(food_log)
        elif choice == '4':
            print("Exiting the program. Stay healthy!")
            break
        else:
            print("Invalid choice, please try again.")

def add_food(food_log):
    food_item = input("Enter the name of the food: ")
    calories = input(f"Enter the calories for {food_item}: ")
    
    try:
        calories = float(calories)
        if food_item in food_log:
            food_log[food_item] += calories
        else:
            food_log[food_item] = calories
        print(f"Added {calories} calories for {food_item}.")
    except ValueError:
        print("Invalid calorie input. Please enter a numeric value.")

def view_total_calories(food_log):
    total_calories = sum(food_log.values())
    print(f"\nTotal calories consumed: {total_calories} kcal")

def view_all_food_items(food_log):
    if not food_log:
        print("\nNo food items logged yet.")
    else:
        print("\nFood items logged:")
        for food_item, calories in food_log.items():
            print(f"{food_item}: {calories} kcal")

if __name__ == "__main__":
    main()
# Calorie1
