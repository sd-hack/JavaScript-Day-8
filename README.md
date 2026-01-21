# JavaScript-Day-8
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Tony's Café Membership Discount</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background: #f2f2f2;
            padding: 40px;
        }
        .card {
            background: white;
            max-width: 400px;
            margin: auto;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }
        h2 { text-align: center; }
        .final { font-weight: bold; color: green; }
    </style>
</head>
<body>

<div class="card" id="output"></div>

<script>
    // Step 1: Membership Type
    let membership = "Silver"; // Gold, Silver, Bronze, Regular
    let billAmount = 800;
    let discount = 0;

    // Step 2: if-else Discount Logic
    if (membership === "Gold") {
        discount = 0.20;
    } else if (membership === "Silver") {
        discount = 0.10;
    } else if (membership === "Bronze") {
        discount = 0.05;
    } else {
        discount = 0;
    }

    // Step 3: Final Amount (if-else)
    let finalIfElse = billAmount - (billAmount * discount);

    // Step 4: Switch Version
    let discount2 = 0;

    switch (membership) {
        case "Gold":
            discount2 = 0.20;
            break;
        case "Silver":
            discount2 = 0.10;
            break;
        case "Bronze":
            discount2 = 0.05;
            break;
        default:
            discount2 = 0;
    }

    let finalSwitch = billAmount - (billAmount * discount2);

    // Step 5: Ternary Welcome Message
    let isMember = membership !== "Regular";
    let message = isMember
        ? "Welcome back, loyal customer! "
        : "Sign up to get discounts!";

    // Display Result Using Template Literals
    document.getElementById("output").innerHTML = `
        <h2>☕ Tony’s Café Bill</h2>
        <p>${message}</p>
        <p><b>Membership:</b> ${membership}</p>
        <p><b>Bill Amount:</b> ₹${billAmount}</p>
        <hr>
        <p class="final">Final Amount (if-else): ₹${finalIfElse}</p>
        <p class="final">Final Amount (switch): ₹${finalSwitch}</p>
    `;
</script>

</body>
</html>
