document.addEventListener('DOMContentLoaded', function () {
  const expenseList = document.querySelector('.expense-list');
  const submitBtn = document.querySelector('.btn-submit-expense');
  const inputExpenseDescription = document.querySelectorAll('.input-expense-description');
  const inputValueDescription = document.querySelectorAll('.input-value-description');
  const expenseTypeDropdownItems = document.querySelectorAll('.dropdown-item');
  const totalSavingsElement = document.getElementById('total-savings');
  const totalExpensesElement = document.getElementById('total-expenses');
  const totalInvestmentsElement = document.getElementById('total-investments');
  const totalEntertainmentElement = document.getElementById('total-entertainment');
  const totalElement = document.getElementById('total');

  let expenses = {
    Savings: [],
    Expense: [],
    Investment: [],
    Entertainment: []
  };

  function updateTotals() {
    let totalSavings = 0;
    let totalExpenses = 0;
    let totalInvestments = 0;
    let totalEntertainment = 0;
    let total = 0;

    for (let category in expenses) {
      expenses[category].forEach(expense => {
        switch (category) {
          case 'Savings':
            totalSavings += expense.value;
            break;
          case 'Expense':
            totalExpenses += expense.value;
            break;
          case 'Investment':
            totalInvestments += expense.value;
            break;
          case 'Entertainment':
            totalEntertainment += expense.value;
            break;
        }
      });
    }

    total = totalSavings + totalExpenses + totalInvestments + totalEntertainment;

    totalSavingsElement.textContent = `$${totalSavings.toFixed(2)}`;
    totalExpensesElement.textContent = `$${totalExpenses.toFixed(2)}`;
    totalInvestmentsElement.textContent = `$${totalInvestments.toFixed(2)}`;
    totalEntertainmentElement.textContent = `$${totalEntertainment.toFixed(2)}`;
    totalElement.textContent = `$${total.toFixed(2)}`;
  }

  submitBtn.addEventListener('click', function () {
    const expenseDescription = inputExpenseDescription[0].value;
    const expenseValue = parseFloat(inputValueDescription[0].value);
    const expenseType = document.querySelector('.btn-info').innerText;

    if (expenseDescription && !isNaN(expenseValue)) {
      const expense = {
        description: expenseDescription,
        value: expenseValue
      };

      expenses[expenseType].push(expense);
      updateTotals();
      renderExpenses();
      inputExpenseDescription.forEach(input => input.value = '');
      inputValueDescription.forEach(input => input.value = '');
    } else {
      alert('Please fill in both fields with valid numbers');
    }
  });

  function renderExpenses() {
    expenseList.innerHTML = '';
    for (let category in expenses) {
      expenses[category].forEach(expense => {
        const listItem = document.createElement('div');
        listItem.classList.add('expense-row');
        listItem.innerHTML = `
          <span>${category}</span>
          <span>${expense.description}</span>
          <span>$${expense.value.toFixed(2)}</span>
        `;
        expenseList.appendChild(listItem);
      });
    }
  }

  expenseTypeDropdownItems.forEach(item => {
    item.addEventListener('click', function () {
      const dropdownToggle = document.getElementById('dropdownking');
      dropdownToggle.innerText = item.innerText;
    });
  });
});
