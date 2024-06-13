# mdx

# BeyondJS Processor for MDX

## Introduction

BeyondJS is an advanced JavaScript framework designed to unify development practices across different environments like
browsers, Node.js, Deno, and Bun. One of its powerful features is the processor system, which includes support for MDX.
MDX allows you to write JSX in Markdown documents, enabling you to use React components within your Markdown content.
The MDX processor in BeyondJS compiles MDX files, making it easier to integrate rich, interactive content in your
applications.

## What is a BeyondJS Processor?

A BeyondJS processor is a tool that handles specific types of files within a project. The MDX processor is responsible
for compiling MDX files, allowing developers to combine Markdown and JSX seamlessly in their applications.

## Setting Up BeyondJS Processor for MDX

### Creating an MDX Module

To create a new MDX module in BeyondJS, you need to create a folder for your module and add a `module.json` file to
configure the MDX processor.

### Example `module.json` Configuration

```json
{
	"name": "contents/en",
	"code": {
		"mdx": {
			"files": ["*"]
		},
		"ts": {
			"files": ["*"]
		}
	}
}
```

In this configuration:

-   The `mdx` entry specifies that all MDX files (`*`) within the module should be processed using the MDX processor.
-   The `ts` entry specifies that all TypeScript files (`*`) within the module should be processed using the TypeScript
    processor.

### Example Directory Structure

```
my-mdx-module/
├── src/
│   ├── content/
│   │   └── example.mdx
│   ├── components/
│   │   └── MyComponent.tsx
│   ├── module.json
```

### Example MDX File (`src/content/example.mdx`)

```mdx
import React from 'react';
import MyComponent from '../components/MyComponent';

# Hello MDX

This is an example of an MDX file in BeyondJS.

<MyComponent />
```

### Example React Component (`src/components/MyComponent.tsx`)

```tsx
import React from 'react';

const MyComponent: React.FC = () => (
	<div>
		<p>This is a React component rendered inside an MDX file.</p>
	</div>
);

export default MyComponent;
```

## Benefits of Using BeyondJS Processor for MDX

1. **Seamless Integration of Markdown and JSX**:

    - Combine the simplicity of Markdown with the power of JSX, enabling rich, interactive content.

2. **Modular Bundling**:

    - Each MDX file is compiled and bundled independently, leading to faster loading times and better performance.

3. **Automatic Compilation**:

    - BeyondJS automatically handles the compilation of MDX files, eliminating the need for manual build steps.

4. **Integration with Other Processors**:
    - Easily integrate the MDX processor with other processors in BeyondJS, such as TypeScript for JavaScript files and
      SASS for CSS files.

## Example Usage in a BeyondJS Project

Here's an example of how to set up a BeyondJS project using the MDX processor alongside other processors.

### `module.json` Configuration

```json
{
	"name": "project",
	"code": {
		"mdx": {
			"files": ["src/content/*.mdx"]
		},
		"ts": {
			"files": ["src/components/*.ts", "src/components/*.tsx"]
		},
		"sass": {
			"files": ["src/styles/*.scss"]
		}
	}
}
```

### Directory Structure

```
my-beyondjs-project/
├── src/
│   ├── components/
│   │   ├── MyComponent.tsx
│   ├── content/
│   │   ├── example.mdx
│   ├── styles/
│   │   └── main.scss
├── module.json
```

### TypeScript Entry File (`src/index.ts`)

```typescript
import './styles/main.scss';
import ExampleContent from './content/example.mdx';

console.log('Hello BeyondJS with MDX!');
```

## Conclusion

The BeyondJS processor for MDX simplifies the development process by automating the compilation of MDX files and
integrating seamlessly with other processors. This modular approach enhances efficiency, performance, and flexibility,
allowing developers to build scalable and maintainable applications. By leveraging the MDX processor in BeyondJS, you
can create rich, interactive content with ease.

---

This README provides a comprehensive overview of setting up and using the MDX processor in a BeyondJS project. By
following these guidelines, you can efficiently manage and render MDX content, enhancing your application's
capabilities.
