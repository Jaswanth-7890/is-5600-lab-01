document.addEventListener("DOMContentLoaded", () => {
    // Select elements
    const userList = document.getElementById("user-list");
    const stockList = document.getElementById("stock-list");
    const userForm = document.getElementById("user-form");
    const deleteUserBtn = document.getElementById("delete-user");

    // Select a user and display portfolio
    userList.addEventListener("click", (event) => {
        if (event.target.classList.contains("user-item")) {
            displayUserPortfolio(event.target.dataset.userId);
        }
    });

    // Select a stock and display details
    stockList.addEventListener("click", (event) => {
        if (event.target.classList.contains("stock-item")) {
            displayStockDetails(event.target.dataset.stockId);
        }
    });

    // Handle user info update
    userForm.addEventListener("submit", (event) => {
        event.preventDefault();
        updateUserInformation();
    });

    // Handle user deletion
    deleteUserBtn.addEventListener("click", () => {
        deleteUser();
    });
});
