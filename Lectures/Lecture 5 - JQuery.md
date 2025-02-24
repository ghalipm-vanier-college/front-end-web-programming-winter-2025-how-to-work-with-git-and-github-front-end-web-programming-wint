## Table of Contents

1. [Introduction to jQuery](#1-introduction-to-jquery)  
   1.1 [What is jQuery?](#11-what-is-jquery)  
   1.2 [Why Use jQuery?](#12-why-use-jquery)  
   1.3 [Including jQuery in a Web Page](#13-including-jquery-in-a-web-page)  

2. [Selecting Elements](#2-selecting-elements)  
   2.1 [Basic Selectors](#21-basic-selectors)  
   2.2 [Attribute Selectors](#22-attribute-selectors)  
   2.3 [Combining Selectors](#23-combining-selectors)  

3. [Handling Events](#3-handling-events)  
   3.1 [Common Event Methods](#31-common-event-methods)  
   3.2 [Event Delegation](#32-event-delegation)  
   3.3 [Binding and Unbinding Events](#33-binding-and-unbinding-events)  

4. [Styling and Animating](#4-styling-and-animating)  
   4.1 [Adding and Removing Classes](#41-adding-and-removing-classes)  
   4.2 [CSS Manipulation](#42-css-manipulation)  
   4.3 [Basic Animations](#43-basic-animations)  
   4.4 [Advanced Animations](#44-advanced-animations)  

5. [Manipulating the DOM](#5-manipulating-the-dom)  
   5.1 [Adding Elements](#51-adding-elements)  
   5.2 [Removing Elements](#52-removing-elements)  
   5.3 [Modifying Content](#53-modifying-content)  


## 1. Introduction to jQuery

### 1.1 What is jQuery?

jQuery is a fast, small, and feature-rich JavaScript library that simplifies tasks such as DOM manipulation, event handling, animation, and AJAX. It provides a more concise and readable syntax compared to plain JavaScript.

### 1.2 Why Use jQuery?

- **Cross-Browser Compatibility**: Handles differences between browsers automatically.
- **Simplified Syntax**: Allows for shorter and more readable code.
- **Extensive Plugin Ecosystem**: A vast library of plugins is available to extend functionality.
- **Rich Features**: Offers built-in methods for DOM manipulation, animations, and AJAX.

### 1.3 Including jQuery in a Web Page

To use jQuery, include it via a CDN or a local file:

```html
<!-- Include jQuery from a CDN -->
<script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>

<!-- OR download and include it locally -->
<script src="path-to-jquery/jquery.min.js"></script>
```

## 2. Selecting Elements

### 2.1 Basic Selectors

jQuery selectors are similar to CSS selectors, making it easy to target elements:

```javascript
// Select by ID
$('#elementID');

// Select by class
$('.className');

// Select by tag
$('div');
```

### 2.2 Attribute Selectors

Use attribute selectors to target elements based on their attributes:

```javascript
// Select input elements with a specific name
$('input[name="username"]');

// Select elements with a specific attribute value
$('a[href="https://example.com"]');
```

### 2.3 Combining Selectors

Combine selectors to narrow down your selection:

```javascript
// Select all divs with a specific class
$('div.className');

// Select all checked checkboxes
$('input[type="checkbox"]:checked');
```

## 3. Handling Events

### 3.1 Common Event Methods

jQuery makes it easy to handle events like `click`, `hover`, and `submit`:

```javascript
// Handle click event
$('#button').click(function () {
  alert('Button clicked!');
});

// Handle hover event
$('#element').hover(
  function () {
    console.log('Mouse entered');
  },
  function () {
    console.log('Mouse left');
  }
);
```

### 3.2 Event Delegation

Use `on()` for dynamically added elements or event delegation:

```javascript
// Delegate click event to dynamically created buttons
$(document).on('click', '.dynamic-button', function () {
  alert('Dynamic button clicked!');
});
```

### 3.3 Binding and Unbinding Events

- **Bind Events**

  ```javascript
  $('#element').on('click', function () {
    console.log('Clicked!');
  });
  ```

- **Unbind Events**

  ```javascript
  $('#element').off('click');
  ```

## 4. Styling and Animating

### 4.1 Adding and Removing Classes

Easily add or remove CSS classes from elements:

```javascript
$('#element').addClass('active');
$('#element').removeClass('active');
$('#element').toggleClass('hidden');
```

### 4.2 CSS Manipulation

Modify CSS properties directly:

```javascript
$('#element').css('color', 'red');
$('#element').css({
  backgroundColor: 'blue',
  fontSize: '16px',
});
```

### 4.3 Basic Animations

jQuery provides simple methods for animations like `hide()`, `show()`, and `fadeOut()`:

```javascript
$('#element').hide();
$('#element').fadeIn();
$('#element').slideUp();
```

### 4.4 Advanced Animations

Use `animate()` for custom animations:

```javascript
$('#element').animate({
  opacity: 0.5,
  height: '50px',
});
```

## 5. Manipulating the DOM

### 5.1 Adding Elements

Insert new elements into the DOM:

```javascript
// Add new content before or after an element
$('#element').before('<p>New content before</p>');
$('#element').after('<p>New content after</p>');

// Append content inside an element
$('#element').append('<span>Appended content</span>');
```

### 5.2 Removing Elements

Remove elements from the DOM:

```javascript
$('#element').remove(); // Completely remove element
$('#element').empty(); // Remove only the content inside
```

### 5.3 Modifying Content

Change the content of elements:

```javascript
$('#element').text('Updated text content');
$('#element').html('<strong>Updated HTML content</strong>');
```
