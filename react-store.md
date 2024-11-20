# Redux

![alt text](image.png)

- One-way data flow
- Immutable:
  Đối với redux khi update state thì nó sẽ tạo ra 1 bản copy của state cũ và lưu lại vào địa chỉ ô nhớ mới thay vì update trực tiếp state cũ. Đối với redux toolkit thì đã tích hợp sẵn immer để làm điều này.

# Redux Toolkit

#### 1. Store

@/store

```javascript
import { configureStore } from "@reduxjs/toolkit";
import { rootReducers } from "./rootReducer";

export const store = configureStore({
  reducer: rootReducers,
});

export type RootState = ReturnType<typeof store.getState>;
export type AppDispatch = typeof store.dispatch;
```

#### 2. Hooks

@/hooks

```javascript
import { useDispatch, useSelector } from 'react-redux'
import { AppDispatch, RootState } from '../store'

// Use throughout your app instead of plain `useDispatch` and `useSelector`
export const useAppDispatch = useDispatch.withTypes<AppDispatch>()
export const useAppSelector = useSelector.withTypes<RootState>()
```

#### 3. Slices

@/features/counter/counterSlice

```javascript
import { createSlice } from "@reduxjs/toolkit";

interface CounterState {
  value: number;
}

const initialState: CounterState = {
  value: 0,
};

export const counterSlice = createSlice({
  name: "counter",
  initialState,
  reducers: {
    increment: (state) => {
      state.value += 1;
    },
    decrement: (state) => {
      state.value -= 1;
    },
  },
});

export const { increment, decrement } = counterSlice.actions;

export default counterSlice.reducer;
```

#### 4. Rootreducer

@/store/rootReducer.ts

```javascript
import { combineReducers } from "@reduxjs/toolkit";
import counterSlice from "../features/counter/counterSlice";

export const rootReducers = combineReducers({
  counter: counterSlice,
});
```

#### Provider

@/main.ts

```javascript
import { StrictMode } from "react";
import { createRoot } from "react-dom/client";
import "./index.css";
import App from "./App.tsx";
import { store } from "./store";
import { Provider } from "react-redux";

createRoot(document.getElementById("root")!).render(
  <StrictMode>
    <Provider store={store}>
      <App />
    </Provider>
  </StrictMode>
);
```

#### 5. Usage

```javascript
import "./App.css";
import { decrement, increment } from "./features/counter/counterSlice";
import { useAppDispatch, useAppSelector } from "./hooks";

function App() {
  const counter = useAppSelector((state) => state.counter.value);
  const dispatch = useAppDispatch();
  return (
    <>
      Counter: {counter}
      <button onClick={() => dispatch(increment())}>+</button>
      <button onClick={() => dispatch(decrement())}>-</button>
    </>
  );
}

export default App;
```
