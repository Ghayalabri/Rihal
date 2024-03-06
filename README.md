<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Event Countdown</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div id="events-container"></div>
  <script src="script.js"></script>
</body>
</html> 

home page :



**HTML (home.html):**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Event Countdown</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <div id="events-container"></div>
  <script src="script.js"></script>
</body>
</html>
```
 **HTML (createEvent.html):**
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Create Event</title>
  <link rel="stylesheet" href="styles.css">
</head>
<body>
  <h1>Create New Event</h1>
  <form id="event-form">
    <input type="text" id="event-name" placeholder="Event Name" required><br>
    <input type="datetime-local" id="event-date" required><br>
    <textarea id="event-description" placeholder="Event Description"></textarea><br>
    <input type="file" id="event-image" accept="image/*"><br>
    <button type="submit">Create Event</button>
  </form>
  <script src="script.js"></script>
</body>
</html>
```


**JavaScript (script.js):**
```javascript
// Home Page
const eventsContainer = document.getElementById('events-container');

function displayEvents(events) {
  eventsContainer.innerHTML = '';
  events.forEach(event => {
    const eventDiv = document.createElement('div');
    eventDiv.classList.add('event');
    eventDiv.innerHTML = `
      <h2>${event.name}</h2>
      <p>${event.description}</p>
      <img src="${event.image}" alt="${event.name}">
      <div class="countdown" data-date="${event.date}"></div>
    `;
    eventsContainer.appendChild(eventDiv);
  });
}

// Event Creation Page
const eventForm = document.getElementById('event-form');

eventForm.addEventListener('submit', function(event) {
  event.preventDefault();
  const eventName = document.getElementById('event-name').value;
  const eventDate = document.getElementById('event-date').value;
  const eventDescription = document.getElementById('event-description').value;
  const eventImage = document.getElementById('event-image').files[0];
  const event = { name: eventName, date: eventDate, description: eventDescription, image: eventImage };
  // Store event in Local Storage
  // Redirect to home.html or display success message
});

// Countdown Timer
const countdowns = document.querySelectorAll('.countdown');

function updateCountdowns() {
  countdowns.forEach(countdown => {
    const eventDate = new Date(countdown.getAttribute('data-date'));
    const currentTime = new Date();
    const timeDifference = eventDate - currentTime;
    const days = Math.floor(timeDifference / (1000 * 60 * 60 * 24));
    const hours = Math.floor((timeDifference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const minutes = Math.floor((timeDifference % (1000 * 60 * 60)) / (1000 * 60));
    const seconds = Math.floor((timeDifference % (1000 * 60)) / 1000);
    countdown.textContent = `${days}d ${hours}h ${minutes}m ${seconds}s`;
  });
}

setInterval(updateCountdowns, 1000);







 **java script**


// Home Page
const eventsContainer = document.getElementById('events-container');

function displayEvents(events) {
  eventsContainer.innerHTML = '';
  events.forEach(event => {
    const eventDiv = document.createElement('div');
    eventDiv.classList.add('event');
    eventDiv.innerHTML = `
      <h2>${event.name}</h2>
      <p>${event.description}</p>
      <img src="${event.image}" alt="${event.name}">
      <div class="countdown" data-date="${event.date}"></div>
    `;
    eventsContainer.appendChild(eventDiv);
  });
}

// Event Creation Page
const eventForm = document.getElementById('event-form');

eventForm.addEventListener('submit', function(event) {
  event.preventDefault();
  const eventName = document.getElementById('event-name').value;
  const eventDate = document.getElementById('event-date').value;
  const eventDescription = document.getElementById('event-description').value;
  const eventImage = document.getElementById('event-image').files[0];
  const event = { name: eventName, date: eventDate, description: eventDescription, image: eventImage };
  // Store event in Local Storage
  // Redirect to home.html or display success message
});

// Countdown Timer
const countdowns = document.querySelectorAll('.countdown');

function updateCountdowns() {
  countdowns.forEach(countdown => {
    const eventDate = new Date(countdown.getAttribute('data-date'));
    const currentTime = new Date();
    const timeDifference = eventDate - currentTime;
    const days = Math.floor(timeDifference / (1000 * 60 * 60 * 24));
    const hours = Math.floor((timeDifference % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
    const minutes = Math.floor((timeDifference % (1000 * 60 * 60)) / (1000 * 60));
    const seconds = Math.floor((timeDifference % (1000 * 60)) / 1000);
    countdown.textContent = `${days}d ${hours}h ${minutes}m ${seconds}s`;
  });
}

setInterval(updateCountdowns, 1000);
