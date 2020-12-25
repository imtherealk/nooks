# @nooks-practice/use-axios

React Hook to use Axios

## Installation

#### yarn

`yarn add @nooks-practice/use-axios`

#### npm

`npm i @nooks-practice/use-axios`

## Usage

```js
import React from "react";
import useAxios from "@nooks-practice/use-axios";

function App() {
  const { loading, data, error, refetch } = useAxios({
    url: "https://yts-proxy.now.sh/list_movies.json"
  });

  return (
    <div className="App">
      <div className="content">
        <h1>{!loading && data && data.status}</h1>
        <h2>{loading && "loading"}</h2>
        <div>{error && error.message}</div>
        <button onClick={refetch}>Refetch</button>
      </div>
    </div>
  );
};
```

### Arguments

| Argument     | Type          | Description                                                                             | Required |
| ------------ | ------------- | --------------------------------------------------------------------------------------- | -------- |
| options      | object        | [Config options for Axios requests](https://www.npmjs.com/package/axios#request-config) | yes      |
| axiosInstance| AxiosInstance | Customized axios instance (or default axios instance)                                   | no       |

### Return

| Return value | Type      | Description                                                     | Default value |
| ------------ | --------- | --------------------------------------------------------------- | ------------- |
| loading      | boolean   | A boolean representing if response is loading or not            | true          |
| error        | object    | Axios error                                                     | null          |
| data         | object    | Axios response data                                             | null          |
| refetch      | function  | Function to refetch data                                        |               |
