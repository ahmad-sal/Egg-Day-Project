```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="Egg Day 2025 — Find egg recipes based on your available ingredients with cost estimation and cooking instructions">
    <title>Egg Day 2025 — Egg Recipes Finder</title>
    <style>
        :root {
            --yolk-yellow: #FFD700;
            --soft-brown: #D2B48C;
            --egg-white: #FFF8DC;
            --dark-brown: #8B4513;
            --light-gray: #f5f5f5;
            --border-color: #ddd;
            --shadow: 0 4px 6px rgba(0,0,0,0.1);
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            background-color: var(--egg-white);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
        }

        header {
            background: linear-gradient(135deg, var(--yolk-yellow), var(--soft-brown));
            color: var(--dark-brown);
            padding: 1.5rem 1rem;
            text-align: center;
            box-shadow: var(--shadow);
        }

        .header-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        h1 {
            font-size: 2.5rem;
            margin-bottom: 0.5rem;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.1);
        }

        .subtitle {
            font-size: 1.2rem;
            margin-bottom: 1rem;
            opacity: 0.9;
        }

        .project-credit {
            font-size: 0.9rem;
            font-weight: bold;
            margin-top: 0.5rem;
            padding: 0.5rem;
            background-color: rgba(255,255,255,0.3);
            border-radius: 20px;
            display: inline-block;
        }

        main {
            flex: 1;
            padding: 2rem 1rem;
            max-width: 1200px;
            margin: 0 auto;
            width: 100%;
        }

        .container {
            display: grid;
            grid-template-columns: 1fr;
            gap: 2rem;
        }

        @media (min-width: 768px) {
            .container {
                grid-template-columns: 300px 1fr;
            }
        }

        .ingredients-section {
            background: white;
            border-radius: 12px;
            padding: 1.5rem;
            box-shadow: var(--shadow);
            height: fit-content;
        }

        .section-title {
            color: var(--dark-brown);
            margin-bottom: 1rem;
            font-size: 1.3rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .ingredients-list {
            max-height: 400px;
            overflow-y: auto;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 0.5rem;
            margin-bottom: 1rem;
        }

        .ingredient-item {
            display: flex;
            align-items: center;
            padding: 0.5rem;
            margin: 0.25rem 0;
            border-radius: 6px;
            transition: var(--transition);
        }

        .ingredient-item:hover {
            background-color: var(--light-gray);
        }

        .ingredient-checkbox {
            margin-right: 0.75rem;
            width: 18px;
            height: 18px;
        }

        .ingredient-info {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            flex: 1;
        }

        .ingredient-icon {
            width: 32px;
            height: 32px;
            background: var(--yolk-yellow);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--dark-brown);
            font-weight: bold;
            font-size: 14px;
        }

        .ingredient-name {
            font-weight: 500;
        }

        .custom-ingredient-form {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
        }

        .custom-input-group {
            display: flex;
            gap: 0.5rem;
        }

        .custom-input {
            flex: 1;
            padding: 0.5rem;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            font-size: 0.9rem;
        }

        .add-btn {
            background: var(--yolk-yellow);
            color: var(--dark-brown);
            border: none;
            padding: 0.5rem 1rem;
            border-radius: 6px;
            cursor: pointer;
            font-weight: bold;
            transition: var(--transition);
        }

        .add-btn:hover {
            background: #e6c200;
            transform: translateY(-1px);
        }

        .find-btn {
            width: 100%;
            background: var(--dark-brown);
            color: white;
            border: none;
            padding: 0.75rem;
            border-radius: 8px;
            font-size: 1.1rem;
            font-weight: bold;
            cursor: pointer;
            margin-top: 1rem;
            transition: var(--transition);
        }

        .find-btn:hover {
            background: #6b360f;
            transform: translateY(-2px);
        }

        .results-section {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .results-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 1rem;
        }

        .surprise-btn {
            background: var(--soft-brown);
            color: var(--dark-brown);
            border: none;
            padding: 0.5rem 1rem;
            border-radius: 6px;
            cursor: pointer;
            font-weight: bold;
            transition: var(--transition);
        }

        .surprise-btn:hover {
            background: #c1a77d;
            transform: translateY(-1px);
        }

        .dishes-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 1.5rem;
        }

        .dish-card {
            background: white;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow);
            transition: var(--transition);
        }

        .dish-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 15px rgba(0,0,0,0.15);
        }

        .dish-image {
            width: 100%;
            height: 200px;
            background: var(--yolk-yellow);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--dark-brown);
            font-weight: bold;
            font-size: 1.2rem;
        }

        .dish-content {
            padding: 1.25rem;
        }

        .dish-header {
            display: flex;
            justify-content: space-between;
            align-items: start;
            margin-bottom: 0.75rem;
        }

        .dish-name {
            font-size: 1.3rem;
            font-weight: bold;
            color: var(--dark-brown);
            margin-bottom: 0.25rem;
        }

        .match-badge {
            background: var(--yolk-yellow);
            color: var(--dark-brown);
            padding: 0.25rem 0.5rem;
            border-radius: 20px;
            font-weight: bold;
            font-size: 0.85rem;
        }

        .dish-meta {
            display: flex;
            gap: 1rem;
            margin-bottom: 0.75rem;
            font-size: 0.9rem;
            color: #666;
        }

        .dish-description {
            margin-bottom: 1rem;
            color: #555;
            font-size: 0.95rem;
        }

        .dish-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .tag {
            background: var(--light-gray);
            padding: 0.25rem 0.5rem;
            border-radius: 12px;
            font-size: 0.8rem;
            color: var(--dark-brown);
        }

        .dish-actions {
            display: flex;
            gap: 0.5rem;
        }

        .action-btn {
            flex: 1;
            padding: 0.5rem;
            border: 1px solid var(--border-color);
            border-radius: 6px;
            background: white;
            cursor: pointer;
            font-size: 0.85rem;
            transition: var(--transition);
        }

        .action-btn:hover {
            background: var(--light-gray);
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.5);
            z-index: 1000;
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background: white;
            border-radius: 12px;
            max-width: 800px;
            max-height: 90vh;
            overflow-y: auto;
            width: 90%;
            padding: 2rem;
            position: relative;
        }

        .close-modal {
            position: absolute;
            top: 1rem;
            right: 1rem;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
            color: #666;
        }

        .recipe-header {
            text-align: center;
            margin-bottom: 2rem;
        }

        .recipe-image {
            width: 100%;
            height: 250px;
            background: var(--yolk-yellow);
            display: flex;
            align-items: center;
            justify-content: center;
            color: var(--dark-brown);
            font-weight: bold;
            font-size: 1.5rem;
            border-radius: 8px;
            margin-bottom: 1.5rem;
        }

        .recipe-meta {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 1.5rem;
            font-weight: bold;
        }

        .recipe-section {
            margin-bottom: 2rem;
        }

        .recipe-section h3 {
            color: var(--dark-brown);
            margin-bottom: 1rem;
            padding-bottom: 0.5rem;
            border-bottom: 2px solid var(--yolk-yellow);
        }

        .ingredients-list-recipe, .steps-list {
            padding-left: 1.5rem;
        }

        .ingredients-list-recipe li, .steps-list li {
            margin-bottom: 0.5rem;
        }

        .missing-ingredients {
            background: #fff3cd;
            border: 1px solid #ffeaa7;
            border-radius: 8px;
            padding: 1rem;
            margin: 1rem 0;
        }

        .shopping-list {
            background: white;
            border-radius: 12px;
            padding: 1.5rem;
            box-shadow: var(--shadow);
            margin-top: 2rem;
        }

        .shopping-list-items {
            margin-top: 1rem;
        }

        .shopping-item {
            display: flex;
            justify-content: space-between;
            padding: 0.5rem 0;
            border-bottom: 1px solid var(--border-color);
        }

        footer {
            background: var(--dark-brown);
            color: white;
            text-align: center;
            padding: 2rem 1rem;
            margin-top: 2rem;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .footer-credit {
            font-size: 1.1rem;
            margin-bottom: 1rem;
            font-weight: bold;
        }

        .help-text {
            max-width: 600px;
            margin: 0 auto;
            font-size: 0.9rem;
            opacity: 0.9;
            line-height: 1.5;
        }

        .user-notes {
            background: var(--yolk-yellow);
            color: var(--dark-brown);
            padding: 1rem;
            border-radius: 8px;
            margin: 1rem 0;
            font-size: 0.9rem;
            text-align: center;
            font-weight: bold;
        }

        /* Print styles */
        @media print {
            .ingredients-section,
            .find-btn,
            .surprise-btn,
            .action-btn,
            footer,
            header {
                display: none !important;
            }
            .modal {
                display: block !important;
                position: static;
                background: white;
                height: auto;
            }
            .modal-content {
                max-height: none;
                overflow: visible;
                padding: 1rem;
            }
            body {
                background: white;
            }
        }

        /* Scrollbar styling */
        .ingredients-list::-webkit-scrollbar {
            width: 8px;
        }

        .ingredients-list::-webkit-scrollbar-track {
            background: var(--light-gray);
            border-radius: 4px;
        }

        .ingredients-list::-webkit-scrollbar-thumb {
            background: var(--yolk-yellow);
            border-radius: 4px;
        }

        .ingredients-list::-webkit-scrollbar-thumb:hover {
            background: #e6c200;
        }
    </style>
</head>
<body>
    <header>
        <div class="header-content">
            <h1>Egg Day 2025 — Egg Recipes Finder</h1>
            <p class="subtitle">Select your available ingredients and discover delicious egg dishes you can make today!</p>
            <div class="project-credit">Project by: Ahmad Saleem & Ahmad Ali — CS 5th Semester</div>
        </div>
    </header>

    <main>
        <div class="user-notes">
            Project for University Egg Day 2025 — authors: Ahmad Saleem & Ahmad Ali — CS 5th. This demo shows client-side recipe suggestion & cost/time estimation.
        </div>

        <div class="container">
            <div class="ingredients-section">
                <h2 class="section-title">Available Ingredients</h2>
                <div class="ingredients-list" id="ingredientsList">
                    <!-- Ingredients will be populated by JavaScript -->
                </div>
                
                <div class="custom-ingredient-form">
                    <h3 class="section-title">Add Custom Ingredient</h3>
                    <div class="custom-input-group">
                        <input type="text" id="customIngredientName" class="custom-input" placeholder="Ingredient name">
                        <input type="number" id="customIngredientPrice" class="custom-input" placeholder="Price per unit" min="0" step="0.01">
                    </div>
                    <button id="addCustomIngredient" class="add-btn">Add Ingredient</button>
                </div>

                <button id="findDishesBtn" class="find-btn">Find Dishes</button>
            </div>

            <div class="results-section">
                <div class="results-header">
                    <h2 class="section-title">Suggested Dishes</h2>
                    <button id="surpriseMeBtn" class="surprise-btn">Surprise Me!</button>
                </div>
                <div class="dishes-grid" id="dishesGrid">
                    <!-- Dishes will be populated by JavaScript -->
                </div>

                <div class="shopping-list" id="shoppingList" style="display: none;">
                    <h2 class="section-title">Shopping List</h2>
                    <div class="shopping-list-items" id="shoppingListItems">
                        <!-- Shopping list items will be populated here -->
                    </div>
                    <div class="shopping-total" id="shoppingTotal"></div>
                </div>
            </div>
        </div>
    </main>

    <div class="modal" id="recipeModal">
        <div class="modal-content">
            <button class="close-modal" id="closeModal">&times;</button>
            <div id="recipeModalContent">
                <!-- Recipe content will be populated here -->
            </div>
        </div>
    </div>

    <footer>
        <div class="footer-content">
            <div class="footer-credit">Egg Day 2025 — Built by Ahmad Saleem & Ahmad Ali, CS 5th Semester • 2025</div>
            <div class="help-text">
                <strong>How to use:</strong> Check the ingredients you have available, click "Find Dishes" to see recipes you can make. 
                Green badges show perfect matches, yellow shows partial matches. Click "Preview Recipe" to see full instructions.
            </div>
        </div>
    </footer>

    <script>
        // IIFE to avoid global namespace pollution
        (function() {
            // Default ingredient prices (per unit)
            const DEFAULT_PRICES = {
                'egg': 15,
                'milk': 0.12, // per ml (120 per liter)
                'flour': 0.08, // per gram (80 per kg)
                'bread': 8, // per slice
                'onion': 20,
                'tomato': 30,
                'cheese': 1, // per gram (200 per 200g = 1 per gram)
                'butter': 0.9, // per gram (180 per 200g)
                'oil': 0.3, // per ml (300 per liter)
                'salt': 0.1,
                'pepper': 0.2,
                'potatoes': 30,
                'spinach': 0.5,
                'mushroom': 2,
                'chicken': 50, // cooked, per 100g
                'sausage': 40,
                'bell pepper': 25,
                'rice': 0.15, // per gram (150 per kg)
                'pasta': 0.2,
                'yogurt': 0.12, // per ml (120 per liter)
                'cilantro': 0.3,
                'chives': 0.4,
                'sugar': 0.1,
                'baking powder': 0.2,
                'soy sauce': 0.5,
                'spring onion': 0.8,
                'peas': 0.3,
                'mayonnaise': 0.8,
                'mustard': 0.6,
                'paprika': 0.4,
                'green chili': 2,
                'spices': 0.5
            };

            // Built-in dishes data
            const DISHES = [
                {
                    id: 1,
                    name: "Classic Omelette",
                    ingredients: [
                        {name: 'egg', qty: 3, unit: 'eggs'},
                        {name: 'milk', qty: 30, unit: 'ml'},
                        {name: 'butter', qty: 10, unit: 'g'},
                        {name: 'salt', qty: 1, unit: 'pinch'},
                        {name: 'pepper', qty: 1, unit: 'pinch'},
                        {name: 'onion', qty: 0.5, unit: 'onion'},
                        {name: 'tomato', qty: 0.5, unit: 'tomato'},
                        {name: 'cheese', qty: 30, unit: 'g'}
                    ],
                    optionalIngredients: [],
                    prepTime: 5,
                    cookTime: 10,
                    servings: 2,
                    difficulty: "easy",
                    tags: ["breakfast", "quick", "protein"],
                    description: "A fluffy, golden omelette filled with vegetables and cheese - perfect for a quick breakfast or brunch.",
                    imageURL: "classic-omelette"
                },
                {
                    id: 2,
                    name: "Egg Fried Rice",
                    ingredients: [
                        {name: 'egg', qty: 2, unit: 'eggs'},
                        {name: 'rice', qty: 200, unit: 'g'},
                        {name: 'oil', qty: 15, unit: 'ml'},
                        {name: 'salt', qty: 1, unit: 'pinch'},
                        {name: 'spring onion', qty: 2, unit: 'stalks'}
                    ],
                    optionalIngredients: [
                        {name: 'peas', qty: 50, unit: 'g'},
                        {name: 'soy sauce', qty: 10, unit: 'ml'}
                    ],
                    prepTime: 10,
                    cookTime: 15,
                    servings: 2,
                    difficulty: "easy",
                    tags: ["dinner", "quick", "asian"],
                    description: "Leftover rice transformed into a delicious meal with scrambled eggs and fresh vegetables.",
                    imageURL: "egg-fried-rice"
                },
                {
                    id: 3,
                    name: "Deviled Eggs",
                    ingredients: [
                        {name: 'egg', qty: 6, unit: 'eggs'},
                        {name: 'mayonnaise', qty: 30, unit: 'g'},
                        {name: 'mustard', qty: 5, unit: 'g'},
                        {name: 'paprika', qty: 1, unit: 'pinch'}
                    ],
                    optionalIngredients: [
                        {name: 'yogurt', qty: 30, unit: 'g'} // substitute for mayo
                    ],
                    prepTime: 20,
                    cookTime: 10,
                    servings: 6,
                    difficulty: "easy",
                    tags: ["appetizer", "party", "snack"],
                    description: "Hard-boiled eggs filled with a creamy, tangy mixture - a classic party appetizer.",
                    imageURL: "deviled-eggs"
                },
                {
                    id: 4,
                    name: "Shakshuka-style Eggs",
                    ingredients: [
                        {name: 'egg', qty: 4, unit: 'eggs'},
                        {name: 'tomato', qty: 3, unit: 'tomatoes'},
                        {name: 'onion', qty: 1, unit: 'onion'},
                        {name: 'bell pepper', qty: 1, unit: 'pepper'},
                        {name: 'oil', qty: 20, unit: 'ml'},
                        {name: 'spices', qty: 2, unit: 'pinch'}
                    ],
                    optionalIngredients: [],
                    prepTime: 15,
                    cookTime: 25,
                    servings: 4,
                    difficulty: "medium",
                    tags: ["breakfast", "dinner", "middle-eastern"],
                    description: "Eggs poached in a spicy tomato and pepper sauce - hearty and flavorful.",
                    imageURL: "shakshuka"
                },
                {
                    id: 5,
                    name: "Egg Toast (Egg-in-a-Hole)",
                    ingredients: [
                        {name: 'bread', qty: 2, unit: 'slices'},
                        {name: 'egg', qty: 2, unit: 'eggs'},
                        {name: 'butter', qty: 10, unit: 'g'},
                        {name: 'salt', qty: 1, unit: 'pinch'}
                    ],
                    optionalIngredients: [],
                    prepTime: 5,
                    cookTime: 10,
                    servings: 2,
                    difficulty: "easy",
                    tags: ["breakfast", "quick", "kid-friendly"],
                    description: "A simple yet satisfying breakfast where eggs are cooked right in the center of buttered toast.",
                    imageURL: "egg-toast"
                },
                {
                    id: 6,
                    name: "Egg Curry (Simple)",
                    ingredients: [
                        {name: 'egg', qty: 4, unit: 'eggs'},
                        {name: 'onion', qty: 1, unit: 'onion'},
                        {name: 'tomato', qty: 2, unit: 'tomatoes'},
                        {name: 'oil', qty: 15, unit: 'ml'},
                        {name: 'spices', qty: 3, unit: 'pinch'}
                    ],
                    optionalIngredients: [],
                    prepTime: 15,
                    cookTime: 20,
                    servings: 4,
                    difficulty: "medium",
                    tags: ["dinner", "indian", "spicy"],
                    description: "Hard-boiled eggs simmered in a rich, spiced tomato-onion gravy.",
                    imageURL: "egg-curry"
                },
                {
                    id: 7,
                    name: "Egg Bhurji (Spiced Scrambled Eggs)",
                    ingredients: [
                        {name: 'egg', qty: 4, unit: 'eggs'},
                        {name: 'onion', qty: 1, unit: 'onion'},
                        {name: 'tomato', qty: 1, unit: 'tomato'},
                        {name: 'green chili', qty: 1, unit: 'chili'},
                        {name: 'oil', qty: 10, unit: 'ml'},
                        {name: 'spices', qty: 2, unit: 'pinch'}
                    ],
                    optionalIngredients: [],
                    prepTime: 10,
                    cookTime: 15,
                    servings: 4,
                    difficulty: "easy",
                    tags: ["breakfast", "indian", "spicy"],
                    description: "Fluffy scrambled eggs cooked with onions, tomatoes, and green chilies - a popular Indian breakfast.",
                    imageURL: "egg-bhurji"
                },
                {
                    id: 8,
                    name: "Spanish Tortilla (Potato-Egg Omelette)",
                    ingredients: [
                        {name: 'egg', qty: 6, unit: 'eggs'},
                        {name: 'potatoes', qty: 3, unit: 'potatoes'},
                        {name: 'onion', qty: 1, unit: 'onion'},
                        {name: 'oil', qty: 50, unit: 'ml'},
                        {name: 'salt', qty: 1, unit: 'pinch'}
                    ],
                    optionalIngredients: [],
                    prepTime: 15,
                    cookTime: 30,
                    servings: 6,
                    difficulty: "medium",
                    tags: ["brunch", "spanish", "hearty"],
                    description: "A thick Spanish omelette made with potatoes and onions - perfect for any meal of the day.",
                    imageURL: "spanish-tortilla"
                },
                {
                    id: 9,
                    name: "Egg Mayo Sandwich",
                    ingredients: [
                        {name: 'bread', qty: 4, unit: 'slices'},
                        {name: 'egg', qty: 3, unit: 'eggs'},
                        {name: 'mayonnaise', qty: 30, unit: 'g'},
                        {name: 'salt', qty: 1, unit: 'pinch'},
                        {name: 'pepper', qty: 1, unit: 'pinch'}
                    ],
                    optionalIngredients: [
                        {name: 'yogurt', qty: 30, unit: 'g'}, // substitute for mayo
                        {name: 'cilantro', qty: 5, unit: 'g'}
                    ],
                    prepTime: 15,
                    cookTime: 10,
                    servings: 2,
                    difficulty: "easy",
                    tags: ["lunch", "sandwich", "quick"],
                    description: "Creamy egg salad sandwich - a classic lunch option that's both satisfying and easy to make.",
                    imageURL: "egg-mayo-sandwich"
                },
                {
                    id: 10,
                    name: "Boiled Egg Salad",
                    ingredients: [
                        {name: 'egg', qty: 4, unit: 'eggs'},
                        {name: 'mayonnaise', qty: 20, unit: 'g'},
                        {name: 'onion', qty: 0.25, unit: 'onion'},
                        {name: 'salt', qty: 1, unit: 'pinch'},
                        {name: 'pepper', qty: 1, unit: 'pinch'},
                        {name: 'lettuce', qty: 50, unit: 'g'}
                    ],
                    optionalIngredients: [
                        {name: 'yogurt', qty: 20, unit: 'g'}, // substitute for mayo
                        {name: 'chives', qty: 5, unit: 'g'}
                    ],
                    prepTime: 15,
                    cookTime: 10,
                    servings: 2,
                    difficulty: "easy",
                    tags: ["salad", "lunch", "healthy"],
                    description: "A refreshing salad featuring hard-boiled eggs with a creamy dressing and fresh vegetables.",
                    imageURL: "boiled-egg-salad"
                }
            ];

            // All available ingredients (including custom ones)
            let allIngredients = [
                'egg', 'milk', 'flour', 'bread', 'onion', 'tomato', 'cheese', 'butter', 'oil', 'salt', 'pepper',
                'potatoes', 'spinach', 'mushroom', 'chicken', 'sausage', 'bell pepper', 'rice', 'pasta', 'yogurt',
                'cilantro', 'chives', 'sugar', 'baking powder', 'soy sauce', 'spring onion', 'peas', 'mayonnaise',
                'mustard', 'paprika', 'green chili', 'spices', 'lettuce'
            ];

            // Custom ingredients added by user
            let customIngredients = {};

            // DOM Elements
            const ingredientsList = document.getElementById('ingredientsList');
            const customIngredientName = document.getElementById('customIngredientName');
            const customIngredientPrice = document.getElementById('customIngredientPrice');
            const addCustomIngredientBtn = document.getElementById('addCustomIngredient');
            const findDishesBtn = document.getElementById('findDishesBtn');
            const dishesGrid = document.getElementById('dishesGrid');
            const surpriseMeBtn = document.getElementById('surpriseMeBtn');
            const recipeModal = document.getElementById('recipeModal');
            const closeModal = document.getElementById('closeModal');
            const recipeModalContent = document.getElementById('recipeModalContent');
            const shoppingList = document.getElementById('shoppingList');
            const shoppingListItems = document.getElementById('shoppingListItems');
            const shoppingTotal = document.getElementById('shoppingTotal');

            // Initialize the application
            function init() {
                renderIngredients();
                setupEventListeners();
                runTests();
            }

            // Render all ingredients with checkboxes
            function renderIngredients() {
                ingredientsList.innerHTML = '';
                
                // Combine default and custom ingredients
                const allIng = [...allIngredients];
                Object.keys(customIngredients).forEach(ing => {
                    if (!allIng.includes(ing)) {
                        allIng.push(ing);
                    }
                });
                
                allIng.sort();
                
                allIng.forEach(ingredient => {
                    const ingredientItem = document.createElement('div');
                    ingredientItem.className = 'ingredient-item';
                    
                    const checkbox = document.createElement('input');
                    checkbox.type = 'checkbox';
                    checkbox.className = 'ingredient-checkbox';
                    checkbox.id = `ing-${ingredient.replace(/\s+/g, '-')}`;
                    checkbox.dataset.ingredient = ingredient;
                    
                    const icon = document.createElement('div');
                    icon.className = 'ingredient-icon';
                    icon.textContent = ingredient.charAt(0).toUpperCase();
                    
                    const name = document.createElement('span');
                    name.className = 'ingredient-name';
                    name.textContent = ingredient;
                    
                    const info = document.createElement('div');
                    info.className = 'ingredient-info';
                    info.appendChild(icon);
                    info.appendChild(name);
                    
                    ingredientItem.appendChild(checkbox);
                    ingredientItem.appendChild(info);
                    
                    ingredientsList.appendChild(ingredientItem);
                });
            }

            // Setup event listeners
            function setupEventListeners() {
                addCustomIngredientBtn.addEventListener('click', addCustomIngredient);
                findDishesBtn.addEventListener('click', findDishes);
                surpriseMeBtn.addEventListener('click', surpriseMe);
                closeModal.addEventListener('click', () => {
                    recipeModal.style.display = 'none';
                });
                
                // Close modal when clicking outside
                recipeModal.addEventListener('click', (e) => {
                    if (e.target === recipeModal) {
                        recipeModal.style.display = 'none';
                    }
                });
            }

            // Add custom ingredient
            function addCustomIngredient() {
                const name = customIngredientName.value.trim();
                const price = parseFloat(customIngredientPrice.value);
                
                if (!name) {
                    alert('Please enter an ingredient name');
                    return;
                }
                
                if (isNaN(price) || price < 0) {
                    alert('Please enter a valid price');
                    return;
                }
                
                // Add to custom ingredients
                customIngredients[name] = price;
                
                // Add to all ingredients if not already present
                if (!allIngredients.includes(name)) {
                    allIngredients.push(name);
                }
                
                // Re-render ingredients list
                renderIngredients();
                
                // Clear inputs
                customIngredientName.value = '';
                customIngredientPrice.value = '';
            }

            // Get selected ingredients
            function getSelectedIngredients() {
                const checkboxes = document.querySelectorAll('.ingredient-checkbox:checked');
                return Array.from(checkboxes).map(cb => cb.dataset.ingredient);
            }

            // Calculate match percentage and missing ingredients
            function calculateMatch(selectedIngredients, dish) {
                const requiredIngredients = dish.ingredients.map(ing => ing.name);
                const optionalIngredients = dish.optionalIngredients.map(ing => ing.name);
                const allRequired = [...requiredIngredients, ...optionalIngredients];
                
                const matched = allRequired.filter(ing => selectedIngredients.includes(ing));
                const missing = allRequired.filter(ing => !selectedIngredients.includes(ing));
                
                const matchPercentage = Math.round((matched.length / allRequired.length) * 100);
                
                return {
                    matchPercentage,
                    missing,
                    matched,
                    allRequired
                };
            }

            // Calculate dish cost
            function calculateDishCost(dish, selectedIngredients) {
                let totalCost = 0;
                const breakdown = [];
                
                // Calculate cost for main ingredients
                dish.ingredients.forEach(ing => {
                    const price = customIngredients[ing.name] || DEFAULT_PRICES[ing.name] || 0;
                    const cost = price * ing.qty;
                    totalCost += cost;
                    if (selectedIngredients.includes(ing.name)) {
                        breakdown.push(`${ing.name}: ${ing.qty} ${ing.unit} × ${price.toFixed(2)} = ${cost.toFixed(2)}`);
                    }
                });
                
                // Calculate cost for optional ingredients (only if selected)
                dish.optionalIngredients.forEach(ing => {
                    if (selectedIngredients.includes(ing.name)) {
                        const price = customIngredients[ing.name] || DEFAULT_PRICES[ing.name] || 0;
                        const cost = price * ing.qty;
                        totalCost += cost;
                        breakdown.push(`${ing.name}: ${ing.qty} ${ing.unit} × ${price.toFixed(2)} = ${cost.toFixed(2)}`);
                    }
                });
                
                return {
                    total: totalCost,
                    breakdown
                };
            }

            // Find and display dishes
            function findDishes() {
                const selectedIngredients = getSelectedIngredients();
                
                if (selectedIngredients.length === 0) {
                    alert('Please select at least one ingredient');
                    return;
                }
                
                // Filter and sort dishes by match percentage
                const dishMatches = DISHES.map(dish => {
                    const match = calculateMatch(selectedIngredients, dish);
                    const cost = calculateDishCost(dish, selectedIngredients);
                    return {
                        ...dish,
                        ...match,
                        cost
                    };
                }).filter(dish => dish.matchPercentage > 0)
                  .sort((a, b) => b.matchPercentage - a.matchPercentage);
                
                renderDishes(dishMatches);
            }

            // Render dishes in grid
            function renderDishes(dishes) {
                dishesGrid.innerHTML = '';
                
                if (dishes.length === 0) {
                    dishesGrid.innerHTML = '<p>No dishes found with your selected ingredients. Try adding more ingredients!</p>';
                    return;
                }
                
                dishes.forEach(dish => {
                    const card = document.createElement('div');
                    card.className = 'dish-card';
                    
                    // Determine badge color based on match percentage
                    let badgeColor = 'background: #28a745; color: white;'; // Green for 100%
                    if (dish.matchPercentage < 100) {
                        badgeColor = 'background: #ffc107; color: #212529;'; // Yellow for partial
                    }
                    
                    card.innerHTML = `
                        <div class="dish-image">${dish.name}</div>
                        <div class="dish-content">
                            <div class="dish-header">
                                <div>
                                    <div class="dish-name">${dish.name}</div>
                                    <div class="dish-meta">
                                        <span>⏱️ ${dish.prepTime + dish.cookTime} min</span>
                                        <span>👥 ${dish.servings} servings</span>
                                        <span>⭐ ${dish.difficulty}</span>
                                    </div>
                                </div>
                                <div class="match-badge" style="${badgeColor}">
                                    ${dish.matchPercentage}% match
                                </div>
                            </div>
                            <p class="dish-description">${dish.description}</p>
                            <div class="dish-tags">
                                ${dish.tags.map(tag => `<span class="tag">${tag}</span>`).join('')}
                            </div>
                            <div class="dish-meta">
                                <strong>Cost: ${dish.cost.total.toFixed(2)}</strong>
                            </div>
                            <div class="dish-actions">
                                <button class="action-btn preview-btn" data-dish-id="${dish.id}">Preview Recipe</button>
                                <button class="action-btn shopping-btn" data-dish-id="${dish.id}">Add to Shopping List</button>
                            </div>
                        </div>
                    `;
                    
                    dishesGrid.appendChild(card);
                });
                
                // Add event listeners to buttons
                document.querySelectorAll('.preview-btn').forEach(btn => {
                    btn.addEventListener('click', (e) => {
                        const dishId = parseInt(e.target.dataset.dishId);
                        const dish = dishes.find(d => d.id === dishId);
                        showRecipeModal(dish);
                    });
                });
                
                document.querySelectorAll('.shopping-btn').forEach(btn => {
                    btn.addEventListener('click', (e) => {
                        const dishId = parseInt(e.target.dataset.dishId);
                        const dish = dishes.find(d => d.id === dishId);
                        addToShoppingList(dish);
                    });
                });
            }

            // Show recipe modal
            function showRecipeModal(dish) {
                const selectedIngredients = getSelectedIngredients();
                const match = calculateMatch(selectedIngredients, dish);
                
                let missingIngredientsHTML = '';
                if (match.missing.length > 0) {
                    missingIngredientsHTML = `
                        <div class="missing-ingredients">
                            <strong>Missing Ingredients:</strong>
                            <ul class="ingredients-list-recipe">
                                ${match.missing.map(ing => `<li>${ing}</li>`).join('')}
                            </ul>
                            <p><em>Tip: You can substitute yogurt for mayonnaise, or use other available ingredients creatively!</em></p>
                        </div>
                    `;
                }
                
                const costBreakdown = dish.cost.breakdown.length > 0 
                    ? `<p><strong>Cost Breakdown:</strong></p><ul class="ingredients-list-recipe">${dish.cost.breakdown.map(item => `<li>${item}</li>`).join('')}</ul>`
                    : '';
                
                recipeModalContent.innerHTML = `
                    <div class="recipe-header">
                        <h2>${dish.name}</h2>
                        <div class="recipe-meta">
                            <span>⏱️ Prep: ${dish.prepTime}min | Cook: ${dish.cookTime}min</span>
                            <span>👥 ${dish.servings} servings</span>
                            <span>⭐ ${dish.difficulty}</span>
                            <span>💰 Total Cost: ${dish.cost.total.toFixed(2)}</span>
                        </div>
                    </div>
                    <div class="recipe-image">${dish.name}</div>
                    ${missingIngredientsHTML}
                    <div class="recipe-section">
                        <h3>Ingredients</h3>
                        <ul class="ingredients-list-recipe">
                            ${dish.ingredients.map(ing => `<li>${ing.qty} ${ing.unit} ${ing.name}</li>`).join('')}
                            ${dish.optionalIngredients.length > 0 ? `<li><em>Optional:</em></li>` + dish.optionalIngredients.map(ing => `<li>${ing.qty} ${ing.unit} ${ing.name}</li>`).join('') : ''}
                        </ul>
                    </div>
                    <div class="recipe-section">
                        <h3>Instructions</h3>
                        <ol class="steps-list">
                            <li>Prepare all ingredients as specified.</li>
                            <li>Follow the cooking method for this specific dish.</li>
                            <li>Cook according to the recommended time and temperature.</li>
                            <li>Serve hot and enjoy your delicious creation!</li>
                        </ol>
                    </div>
                    ${costBreakdown}
                    <button class="find-btn" onclick="window.print()">Print Recipe</button>
                `;
                
                recipeModal.style.display = 'flex';
            }

            // Add dish to shopping list
            function addToShoppingList(dish) {
                const selectedIngredients = getSelectedIngredients();
                const match = calculateMatch(selectedIngredients, dish);
                
                if (match.missing.length === 0) {
                    alert('You have all the ingredients needed for this dish!');
                    return;
                }
                
                // Show shopping list
                shoppingList.style.display = 'block';
                
                // Clear existing items
                shoppingListItems.innerHTML = '';
                
                let totalShoppingCost = 0;
                
                // Add missing ingredients to shopping list
                match.missing.forEach(ingredient => {
                    // Find the ingredient in dish ingredients or optional ingredients
                    let ingInfo = dish.ingredients.find(i => i.name === ingredient) || 
                                 dish.optionalIngredients.find(i => i.name === ingredient);
                    
                    if (ingInfo) {
                        const price = customIngredients[ingredient] || DEFAULT_PRICES[ingredient] || 0;
                        const cost = price * ingInfo.qty;
                        totalShoppingCost += cost;
                        
                        const shoppingItem = document.createElement('div');
                        shoppingItem.className = 'shopping-item';
                        shoppingItem.innerHTML = `
                            <span>${ingInfo.qty} ${ingInfo.unit} ${ingredient}</span>
                            <span>${cost.toFixed(2)}</span>
                        `;
                        shoppingListItems.appendChild(shoppingItem);
                    }
                });
                
                shoppingTotal.innerHTML = `<strong>Total Shopping Cost: ${totalShoppingCost.toFixed(2)}</strong>`;
            }

            // Surprise me button - select random dish
            function surpriseMe() {
                const randomDish = DISHES[Math.floor(Math.random() * DISHES.length)];
                
                // Select all ingredients for this dish
                const allDishIngredients = [
                    ...randomDish.ingredients.map(ing => ing.name),
                    ...randomDish.optionalIngredients.map(ing => ing.name)
                ];
                
                // Check all relevant checkboxes
                document.querySelectorAll('.ingredient-checkbox').forEach(checkbox => {
                    const ingredient = checkbox.dataset.ingredient;
                    checkbox.checked = allDishIngredients.includes(ingredient);
                });
                
                // Find and display dishes
                findDishes();
                
                // Scroll to results
                dishesGrid.scrollIntoView({ behavior: 'smooth' });
            }

            // Simple unit tests
            function runTests() {
                console.log('Running unit tests...');
                
                // Test 1: Match calculation
                const testSelected = ['egg', 'milk', 'butter', 'salt', 'pepper'];
                const testDish = DISHES[0]; // Classic Omelette
                const match = calculateMatch(testSelected, testDish);
                console.assert(match.matchPercentage === 62, `Expected 62%, got ${match.matchPercentage}%`);
                
                // Test 2: Cost calculation
                const cost = calculateDishCost(testDish, testSelected);
                const expectedCost = (15 * 3) + (0.12 * 30) + (0.9 * 10) + (0.1 * 1) + (0.2 * 1);
                console.assert(Math.abs(cost.total - expectedCost) < 0.01, `Expected cost ~${expectedCost}, got ${cost.total}`);
                
                console.log('Unit tests completed!');
            }

            // Initialize the app when DOM is loaded
            if (document.readyState === 'loading') {
                document.addEventListener('DOMContentLoaded', init);
            } else {
                init();
            }
        })();
    </script>
</body>
</html>
```
