const form = document.getElementById('transaction-form');
const type = document.getElementById('type');
const category = document.getElementById('category');
const amount = document.getElementById('amount');
const history = document.getElementById('history');
const incomeDisplay = document.getElementById('income');
const expenseDisplay = document.getElementById('expense');
const balanceDisplay = document.getElementById('balance');

let transactions = [];

form.addEventListener('submit', function (e) {
  e.preventDefault();

  const transaction = {
    type: type.value,
    category: category.value,
    amount: parseFloat(amount.value)
  };

  transactions.push(transaction);
  updateDisplay();
  form.reset();
});

function updateDisplay() {
  history.innerHTML = "";
  let income = 0, expense = 0;

  transactions.forEach(t => {
    const item = document.createElement('li');
    item.textContent = `${t.type} | ${t.category} | $${t.amount.toFixed(2)}`;
    history.appendChild(item);

    if (t.type === "Income") income += t.amount;
    else if (t.type === "Expense") expense += t.amount;
  });

  incomeDisplay.textContent = income.toFixed(2);
  expenseDisplay.textContent = expense.toFixed(2);
  balanceDisplay.textContent = (income - expense).toFixed(2);
}
