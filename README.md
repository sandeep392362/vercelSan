// Define the interface for the expected response data structure
interface Todo {
  userId: number;
  id: number;
  title: string;
  completed: boolean;
}

// Function to fetch data from the API
async function fetchData() {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/todos/1');
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    const data: Todo = await response.json();
    console.log('Data:', data);
  } catch (error) {
    console.error('Error fetching data:', error);
  }
}

// Call the fetchData function
fetchData();
