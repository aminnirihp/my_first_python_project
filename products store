import json
import os

store_file = "store.json"

# -------- LOAD DATA --------
if os.path.exists(store_file):
    with open(store_file, "r", encoding="utf-8") as f:
        try:
            store = json.load(f)
        except:
            store = {}
else:
    store = {}

# SAVE FUNCTION 
def save_store():
    with open(store_file, "w", encoding="utf-8") as f:
        json.dump(store, f, ensure_ascii=False, indent=4)

# MENU 
def show_menu():
    print("\n--- STORE MENU ---")
    print("1. Add product")
    print("2. Remove product")
    print("3. Update product")
    print("4. Search product")
    print("5. Show all products")
    print("6. Exit")

#  MAIN LOOP 
while True:
    show_menu()
    choice = input("Enter your choice: ")

    # ADD PRODUCT
    if choice == "1":
         name = input("Name of new product: ").strip()
         price = int(input("Price: "))
         qty = int(input("Quantity: "))
         category = input("Category: ").strip()

         store[name] = {
           "price": price,
           "quantity": qty,
           "category": category
         }

         save_store()
         print("Product added")


    # REMOVE PRODUCT
    elif choice == "2":
        name = input("Name of product to delete: ").strip()
        if name in store:
            del store[name]
            save_store()
            print("Deleted successfully")
        else:
            print("Product not found")

    # UPDATE PRODUCT
    elif choice == "3":
        name = input("Name of product to update: ").strip()
        if name in store:
            new_price = int(input("New price: "))
            store[name] = new_price
            save_store()
            print("Updated!")
        else:
            print("Product not found")

    # SEARCH PRODUCT
    elif choice == "4":
        name = input("Product name to search: ").strip()
        if name in store:
            print("Price:", store[name])
        else:
            print("Product not found")

    # SHOW ALL
    elif choice == "5":
        if not store:
            print('store is epmty')
        else:
            for name, info in store.items():
                print(f'{name}--->{info['price']}')

    # EXIT
    elif choice == "6":
        print("Exiting program...")
        break

    else:
        print("Invalid choice")
