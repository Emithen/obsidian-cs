
#### Normal virtual function
```
class Animal {
public:
    virtual void speak() {
        cout << "Animal sound\n";
    }
};

// // // // //

Animal a; // 가능
a.speak(); // "Animal sound"

```
#### Pure virtual function
```
class Animal {
public:
    virtual void speak() = 0;
};

// // // // //

Animal a; // 불가능 (추상 클래스)
```
