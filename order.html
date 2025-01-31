document.addEventListener('DOMContentLoaded', function() {
    document.getElementById('orderButton').addEventListener('click', function() {
        document.getElementById('orderFormContainer').style.display = 'block';
    });
});

function addItem() {
    const menu = document.querySelector('.menu').value;
    const quantity = document.querySelector('.quantity').value;
    const price = parseFloat(document.querySelector('.menu option:checked').getAttribute('data-price'));
    const itemName = document.querySelector('.menu option:checked').text;

    if (quantity > 0) {
        const selectedItems = document.getElementById('selectedItems');
        const row = document.createElement('tr');

        row.innerHTML = `
            <td>${itemName}</td>
            <td><input type="number" class="item-quantity" value="${quantity}" min="1" onchange="updateItem(this)"></td>
            <td class="item-price">£${(price * quantity).toFixed(2)}</td>
            <td><button type="button" onclick="removeItem(this)">Remove</button></td>
        `;

        row.setAttribute('data-price', price);
        selectedItems.appendChild(row);

        updateTotal();
    }
}

function updateItem(element) {
    const row = element.closest('tr');
    const price = parseFloat(row.getAttribute('data-price'));
    const quantity = element.value;
    const itemPrice = row.querySelector('.item-price');

    itemPrice.textContent = `£${(price * quantity).toFixed(2)}`;
    updateTotal();
}

function removeItem(button) {
    const row = button.closest('tr');
    row.remove();
    updateTotal();
}

function updateTotal() {
    const selectedItems = document.querySelectorAll('#selectedItems tr');
    let totalPrice = 0;

    selectedItems.forEach(item => {
        const itemPrice = parseFloat(item.querySelector('.item-price').textContent.replace('£', ''));
        totalPrice += itemPrice;
    });

    const coupon = document.getElementById('coupon').value;
    if (coupon === 'DISCOUNT10') {
        totalPrice *= 0.9; // 10% discount
    }

    document.getElementById('totalPrice').innerText = `Total Price: £${totalPrice.toFixed(2)}`;
}

document.getElementById('orderForm').addEventListener('submit', function(event) {
    event.preventDefault();

    const name = document.getElementById('name').value;
    const email = document.getElementById('email').value;
    const phone = document.getElementById('phone').value;
    const selectedItems = document.querySelectorAll('#selectedItems tr');
    const orders = [];

    selectedItems.forEach(item => {
        const menu = item.querySelector('td').textContent;
        const quantity = item.querySelector('.item-quantity').value;
        orders.push({ menu, quantity });
    });

    const totalPrice = document.getElementById('totalPrice').innerText.split('£')[1];

    fetch('https://api.github.com/repos/YOUR_USERNAME/YOUR_REPOSITORY/dispatches', {
        method: 'POST',
        headers: {
            'Accept': 'application/vnd.github.v3+json',
            'Authorization': 'token YOUR_GITHUB_TOKEN',
            'Content-Type': 'application/json'
        },
        body: JSON.stringify({
            event_type: 'order_placed',
            client_payload: { name, email, phone, orders, totalPrice }
        })
    })
    .then(response => response.json())
    .then(data => alert('Order placed successfully!'))
    .catch(error => console.error('Error:', error));
});
