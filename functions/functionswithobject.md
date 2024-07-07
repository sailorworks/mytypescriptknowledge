# Function with object
```
// Define the Product interface
interface Product {
  name: string;
  stock: number;
  price: number;
  photo: string;
  readonly id: string;
}

// Define the GetDataType type alias for a function signature
type GetDataType = (product: Product) => void;

// Define a function getData with the GetDataType signature
const getData: GetDataType = (product) => {
  // Log the product object to the console
  console.log(product);
};

// Create a product object that conforms to the Product interface
const productOne: Product = {
  name: "Macbook",
  stock: 46,
  price: 999999,
  photo: "samplephotourl",
  id: "asdnasjdasjkdas", // readonly field
};

// Call the getData function with the productOne object
getData(productOne); // This will log the productOne object to the console
```

You just need to understand this code snippet

- we have created an object named product.
- then we have created a function named ``GetDataType``, it is taking Product that is an object created as an argument.
- after this we have created a function ``GetData`` that has type ``GetDataType`` .
- the rest of the code in that function is returntype.