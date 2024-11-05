<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Restaurant Order Form</title>
    <style>
        body {
            font-family: Arial, sans-serif;
        }
        .container {
            width: 80%;
            margin: 0 auto;
        }
        h1 {
            text-align: center;
        }
        form {
            margin-bottom: 20px;
        }
        .menu-category {
            margin-bottom: 20px;
        }
        .summary {
            margin-top: 40px;
            border-top: 2px solid #000;
            padding-top: 20px;
        }
        table {
            width: 100%;
            border-collapse: collapse;
        }
        table, th, td {
            border: 1px solid black;
        }
        th, td {
            padding: 10px;
            text-align: left;
        }
        .button-container {
            text-align: center;
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Restaurant Menu & Order Form</h1>

        <!-- Page 1: Order Form -->
        <div id="page1">
            <form id="orderForm">
                <label for="name">Your Name:</label><br>
                <input type="text" id="name" name="name" required><br><br>

                <!-- Drinks Section -->
                <div class="menu-category">
                    <h3>Drinks</h3>
                    <label><input type="checkbox" name="item" value="Coffee Milk - 28K"> Coffee Milk - 28K</label><br>
                    <label><input type="checkbox" name="item" value="Bracce Latte - 28K"> Bracce Latte - 28K</label><br>
                    <label><input type="checkbox" name="item" value="Chocolate - 28K"> Chocolate - 28K</label><br>
                </div>

                <!-- Snacks Section -->
                <div class="menu-category">
                    <h3>Snacks</h3>
                    <label><input type="checkbox" name="item" value="Tofu Crispy - 28K"> Tofu Crispy - 28K</label><br>
                    <label><input type="checkbox" name="item" value="French Fries - 25K"> French Fries - 25K</label><br>
                </div>

                <!-- Submit Button -->
                <button type="submit">Submit Order</button>
            </form>
        </div>

        <!-- Page 2: Order Summary -->
        <div id="page2" style="display: none;">
            <h2>Order Summary</h2>
            <table id="orderSummary">
                <thead>
                    <tr>
                        <th>Name</th>
                        <th>Order</th>
                    </tr>
                </thead>
                <tbody>
                </tbody>
            </table>

            <div class="button-container">
                <button onclick="goBackToOrderForm()">Add Another Order</button>
            </div>
        </div>
    </div>

    <script>
        // Handle the form submission
        document.getElementById('orderForm').addEventListener('submit', function (e) {
            e.preventDefault();

            const name = document.getElementById('name').value;
            const selectedItems = Array.from(document.querySelectorAll('input[name="item"]:checked'))
                                      .map(item => item.value);

            if (!name || selectedItems.length === 0) {
                alert("Please enter your name and select at least one item.");
                return;
            }

            // Add the order to the summary table
            const summaryTable = document.querySelector('#orderSummary tbody');
            const newRow = document.createElement('tr');
            newRow.innerHTML = `<td>${name}</td><td>${selectedItems.join(', ')}</td>`;
            summaryTable.appendChild(newRow);

            // Clear the form and show the summary page
            document.getElementById('orderForm').reset();
            showOrderSummary();
        });

        // Show the order summary page (Page 2)
        function showOrderSummary() {
            document.getElementById('page1').style.display = 'none';
            document.getElementById('page2').style.display = 'block';
        }

        // Go back to the order form to add more orders (Page 1)
        function goBackToOrderForm() {
            document.getElementById('page1').style.display = 'block';
            document.getElementById('page2').style.display = 'none';
        }
    </script>
</body>
</html>
