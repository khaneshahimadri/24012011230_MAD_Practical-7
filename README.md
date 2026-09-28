# 📱 MAD Practical 7 – RecyclerView Contact List Application

![Language](https://img.shields.io/badge/Language-Kotlin-purple)
![Platform](https://img.shields.io/badge/Platform-Android-green)
![IDE](https://img.shields.io/badge/IDE-Android%20Studio-blue)
![Course](https://img.shields.io/badge/Subject-Mobile%20Application%20Development-orange)

## 📌 Practical Information

**Name:** Himadri Khanesha  
**Enrollment No.:** 24012011230  
**Class:** CE-I  
**Batch:** I-2  
**Subject:** Mobile Application Development (MAD)  
**Practical No.:** 7  

---

## 🎯 Aim

To develop an Android application using **RecyclerView** for displaying a list of contacts and implement user interaction to view contact information using **Kotlin**.

---

## 📖 About the Project

This Android application demonstrates the implementation of a **RecyclerView** for displaying multiple contacts efficiently.

Each contact is represented using a custom item layout. The application uses a **Person data model** to store contact information and a custom **RecyclerView Adapter** to bind the contact data to the user interface.

When a user selects a contact, the application can navigate to another Activity using an **Intent** and pass the selected contact information.

---

## ✨ Features

- 📋 Display multiple contacts using RecyclerView
- 👤 Store contact information using a Person model
- 🧩 Custom layout for every RecyclerView item
- 🔄 Efficient list rendering using RecyclerView
- 🖱️ Handle click events on individual contacts
- 🚀 Navigate between Activities using Intent
- 📤 Pass contact information between Activities
- 🎨 Clean and simple Android UI
- ⚡ Dynamic data binding using a custom Adapter

---

## 🧠 Concepts Covered

This practical demonstrates several important Android development concepts:

### 1. RecyclerView

`RecyclerView` is used to efficiently display a large or dynamic collection of items.

It reuses item views instead of creating a completely new view for every item.

### 2. RecyclerView Adapter

The custom `Contact_adapter` connects the contact data with the RecyclerView.

The adapter mainly uses:

- `onCreateViewHolder()`
- `onBindViewHolder()`
- `getItemCount()`

### 3. ViewHolder

The `ViewHolder` stores references to the views of each RecyclerView item.

This improves performance by avoiding repeated view lookups.

### 4. Person Model Class

The `Person` class represents the data of an individual contact.

It is used to organize and manage contact information before displaying it in the RecyclerView.

### 5. ArrayList

An `ArrayList<Person>` is used to store multiple contact objects dynamically.

Example concept:

```kotlin
val contactList = ArrayList<Person>()
```

### 6. LayoutInflater

`LayoutInflater` converts the XML layout of a RecyclerView item into an Android `View`.

```kotlin
LayoutInflater.from(parent.context)
    .inflate(R.layout.single_item, parent, false)
```

### 7. Intent

Intent is used to move from one Activity to another.

```kotlin
val intent = Intent(context, SecondActivity::class.java)
context.startActivity(intent)
```

### 8. Intent Extras

Selected contact information can be transferred to another Activity using Intent extras.

```kotlin
intent.putExtra("name", person.name)
```

The next Activity can retrieve the value using:

```kotlin
intent.getStringExtra("name")
```

---

## 🔄 Application Workflow

```text
Application Starts
       ↓
MainActivity
       ↓
Create Contact List
       ↓
ArrayList<Person>
       ↓
RecyclerView
       ↓
Contact_adapter
       ↓
onCreateViewHolder()
       ↓
Create single_item Layout
       ↓
onBindViewHolder()
       ↓
Display Contact Information
       ↓
User Selects Contact
       ↓
Intent
       ↓
Open Contact Details Activity
       ↓
Display Selected Contact Information
```

---

## 🏗️ Project Architecture

```text
MainActivity
     │
     │ creates
     ▼
ArrayList<Person>
     │
     │ passed to
     ▼
Contact_adapter
     │
     │ binds data to
     ▼
RecyclerView
     │
     │ uses
     ▼
single_item.xml
     │
     │ user clicks item
     ▼
Intent
     │
     ▼
Contact Details Activity
```

---

## 📂 Project Structure

```text
24012011230_MAD_Practical-7/
│
├── app/
│   ├── src/
│   │   └── main/
│   │       │
│   │       ├── java/
│   │       │   └── com.example.a24012011230_mad_practical_7/
│   │       │       ├── MainActivity.kt
│   │       │       ├── Contact_adapter.kt
│   │       │       └── Person.kt
│   │       │
│   │       ├── res/
│   │       │   ├── layout/
│   │       │   │   ├── activity_main.xml
│   │       │   │   └── single_item.xml
│   │       │   │
│   │       │   ├── drawable/
│   │       │   ├── mipmap/
│   │       │   └── values/
│   │       │
│   │       └── AndroidManifest.xml
│   │
│   └── build.gradle.kts
│
├── gradle/
├── build.gradle.kts
├── settings.gradle.kts
└── README.md
```

---

## 🧩 Important Files

### 📄 `MainActivity.kt`

MainActivity acts as the main controller of the application.

Its responsibilities include:

- Initializing RecyclerView
- Creating contact objects
- Adding contacts to the ArrayList
- Setting the LayoutManager
- Creating the Adapter
- Connecting the Adapter with RecyclerView

---

### 📄 `Person.kt`

The `Person` class works as the **data model** of the application.

It represents information related to each contact.

```text
Person
  │
  ├── Name
  ├── Phone Number
  └── Other Contact Information
```

Each Person object represents one item displayed inside the RecyclerView.

---

### 📄 `Contact_adapter.kt`

This is the custom RecyclerView Adapter.

```kotlin
class Contact_adapter(
    val contactlist: ArrayList<Person>
) : RecyclerView.Adapter<Contact_adapter.ContactViewHolder>()
```

Its major responsibilities are:

```text
Contact_adapter
      │
      ├── onCreateViewHolder()
      │       ↓
      │   Creates item View
      │
      ├── onBindViewHolder()
      │       ↓
      │   Binds Person data
      │
      └── getItemCount()
              ↓
          Returns list size
```

---

### 📄 `single_item.xml`

This XML file defines how **one contact item** appears inside the RecyclerView.

RecyclerView repeatedly uses this layout for every contact.

```text
RecyclerView
│
├── single_item → Contact 1
├── single_item → Contact 2
├── single_item → Contact 3
├── single_item → Contact 4
└── single_item → Contact 5
```

---

## ⚙️ RecyclerView Working

The complete working process can be understood as:

```text
Data
 ↓
Person Objects
 ↓
ArrayList<Person>
 ↓
Contact_adapter
 ↓
ViewHolder
 ↓
single_item.xml
 ↓
RecyclerView
 ↓
User Interface
```

The adapter acts as a **bridge between the data and RecyclerView UI**.

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Kotlin | Application programming |
| Android Studio | Development environment |
| XML | User interface design |
| RecyclerView | Display dynamic lists |
| ViewHolder | Efficient view management |
| ArrayList | Store contact objects |
| Intent | Activity navigation |
| Gradle | Android build system |

---

## 🚀 How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/khaneshahimadri/24012011230_MAD_Practical-7.git
```

### 2. Open Android Studio

Select:

```text
File → Open
```

and open the cloned project.

### 3. Sync Gradle

Allow Android Studio to complete the Gradle synchronization.

### 4. Select Device

Use either:

- Android Emulator
- Physical Android Device

### 5. Run Application

Click:

```text
▶ Run
```

The contact list application will launch on the selected Android device.

---

## 🎓 Learning Outcomes

After completing this practical, I learned how to:

- Implement RecyclerView in Android
- Create custom RecyclerView adapters
- Understand the ViewHolder pattern
- Create custom XML item layouts
- Store objects using ArrayList
- Bind Kotlin data with Android UI components
- Handle RecyclerView item click events
- Navigate between Activities
- Transfer information using Intent
- Structure an Android project properly

---

## 💡 Why RecyclerView?

RecyclerView is preferred for displaying lists because it provides:

- Better performance
- View recycling
- Flexible layouts
- Easy customization
- Efficient memory usage
- Support for large datasets

Instead of creating a completely new View for every item, RecyclerView **reuses existing item views**, making the application more efficient.

---

## 🔑 Key Takeaway

The most important concept demonstrated in this practical is:

> **RecyclerView + Adapter + ViewHolder + Model Class**

These components work together to create an efficient and dynamic list-based Android application.

```text
Model (Person)
      ↓
ArrayList
      ↓
Adapter
      ↓
ViewHolder
      ↓
RecyclerView
      ↓
User Interface
```

---

## 👩‍💻 Author

**Himadri Khanesha**

B.Tech – Computer Engineering  
U.V. Patel College of Engineering (UVPCE)  
Ganpat University

**Enrollment No.:** 24012011230

---

## 🔗 Repository

[24012011230_MAD_Practical-7](https://github.com/khaneshahimadri/24012011230_MAD_Practical-7)

---
