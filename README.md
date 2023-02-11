# Nammatham Starter

[Nammatham](https://github.com/mildronize/nammatham) (นามธรรม in Thai, pronounced `/naam ma tham/`) is Azure Function Nodejs Lightweight frameworks with Dependency Injection, 

## Introduction

Azure Functions is a platform for building event-driven and serverless applications. **Nammatham** is a framework that allows you to use Azure Functions with TypeScript and decorators. It provides pre-defined JSON binding objects and utility functions, such as `httpTrigger`, to make it easier to create Azure Functions.

One example of using Nammatham with Azure Functions is an HTTP trigger function, where the `httpTrigger` function returns a JSON binding object that defines the function's input and output. The `@controller` and `@functionName` decorators are used to define the function and specify its bindings.

```ts
import { AuthorizationLevel, BaseFunction, functionName, httpTrigger } from "nammatham";
import { HttpRequest } from "@azure/functions";

@functionName("GetUsers", httpTrigger(AuthorizationLevel.Anonymous, ["get"]))
export class UserFunction extends BaseFunction {

  public override execute(req: HttpRequest): void {
    const name = req.query.name;  
    this.res.send(`hello get user with ${name}`);
  }
}
```

## Getting Started

Dev

```bash
npm run dev
```

Build

```bash
npm run build
```
