# Use Zod to validate File input

You can use [Zod](https://zod.dev/)'s `instanceof` validator to validate file inputs:

```js
const MAX_UPLOAD_SIZE = 1024 * 1024 * 3; // 3MB
const ACCEPTED_FILE_TYPES = ['image/png'];

const Schema = z
  .instanceof(File)
  .optional()
  .refine((file) => {
    return !file || file.size <= MAX_UPLOAD_SIZE;
  }, 'File size must be less than 3MB')
  .refine((file) => {
    return ACCEPTED_FILE_TYPES.includes(file.type);
  }, 'File must be a PNG');
```

Above example validates the file is the correct max file size and file type.
