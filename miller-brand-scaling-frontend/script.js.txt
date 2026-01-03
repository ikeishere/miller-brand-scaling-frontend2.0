document.getElementById("subscribeBtn").addEventListener("click", async () => {
  try {
    const response = await fetch("https://YOUR-BACKEND-URL/create-checkout-session", {
      method: "POST",
    });

    const data = await response.json();
    if (data.url) {
      window.location.href = data.url;
    } else {
      alert("Something went wrong. Please try again.");
    }
  } catch (error) {
    console.error("Error:", error);
    alert("Failed to connect to server.");
  }
});
