# Blobify

Blobify is a simple npm package that provides an easy way to work with binary data using JavaScript's Blob object. This package allows you to convert data from various sources into Blob objects, which can be particularly useful for handling files, streams, and other types of binary data.

## Installation

You can install Blobify using npm:

```bash
npm install blobify
```

## Usage

Using Blobify is straightforward. Once you've installed the package, you can import and use it in your code like this:

1. Import the Blobify module:

```javascript
import Blobify from 'blobify';
```

2. Convert data to a Blob:

```javascript
const yourFunction = async () => {
  // Replace 'your_uri' with the actual URI or data you want to convert
  const blob = await Blobify('your_uri');

  // Don't forget to release the resources when you're done
  blob.close();
};
```

## API Reference

### Blobify(uri: string): Promise&lt;Blob&gt;

The main function provided by the Blobify package. It takes a URI or data as input and returns a Promise that resolves to a Blob object containing the converted data.

- `uri` (string): The URI or data that you want to convert into a Blob.

### Blob.close()

Closes the Blob, releasing its resources. This method should be called when you're done working with the Blob to avoid memory leaks.

## Example

Here's an example of using Blobify to convert an image URL into a Blob and display it on a web page:

```javascript
import Blobify from 'blobify';

const displayImage = async (imageUrl) => {
  const blob = await Blobify(imageUrl);

  const blobUrl = URL.createObjectURL(blob);
  const imgElement = document.createElement('img');
  imgElement.src = blobUrl;
  document.body.appendChild(imgElement);

  blob.close();
};

const imageUrl = 'https://example.com/image.jpg';
displayImage(imageUrl);
```

## Conclusion

Blobify simplifies the process of working with binary data in JavaScript by providing an intuitive way to convert data into Blob objects. With its easy-to-use interface, you can seamlessly handle files, streams, and other binary data sources. Remember to close the Blob objects when you're done using them to free up resources.

If you encounter any issues or have suggestions for improvement, feel free to [report them on GitHub](https://github.com/JHOW2004/blobfy.git).

Happy coding!
