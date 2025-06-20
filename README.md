# Undo/Redo String History in C++

This project demonstrates a simple implementation of undo and redo functionality using C++ with the help of `std::stack` and `__declspec(property)` to simulate property-like access similar to C#.

## 🧠 Features

- Set string values with history tracking
- Undo and redo previous values
- Uses two stacks internally: one for undo history, one for redo history
- Clean and simple interface using `Value` as a property

## 📁 Files

- `clsMyString.h` — The main class implementing the undo/redo logic
- `main.cpp` — A test driver demonstrating how the undo/redo system works

## 🔧 How It Works

- `Set(string value)`: Pushes the current value onto the undo stack and sets the new value.
- `Undo()`: Pops the last value from the undo stack, pushes the current value to the redo stack, and restores the previous value.
- `Redo()`: Pops from the redo stack and re-applies a previously undone value.

## ✅ Sample Output

```plaintext
S1  = 
S1  = Mohammed
S1  = Mohammed2
S1  = Mohammed3

Undo: 
__________

S1  after undo = Mohammed2
S1  after undo = Mohammed
S1  after undo = 

Redo: 
__________

S1  after Redo = Mohammed
S1  after Redo = Mohammed2
S1  after Redo = Mohammed3
````

## 🧪 Example Usage

```cpp
clsMyString s;
s.Value = "Hello";
s.Value = "World";
s.Undo(); // -> "Hello"
s.Redo(); // -> "World"
```

## ⚙️ Requirements

* Windows with MSVC (due to `__declspec(property)`)
* C++11 or later
* No external dependencies

## 📌 Notes

* The use of `__declspec(property)` is Microsoft-specific and will not compile on GCC or Clang.
* For cross-platform compatibility, replace the property syntax with traditional getter/setter methods (`Get()` and `Set()`).

## 📜 License

This project is released under the MIT License.
