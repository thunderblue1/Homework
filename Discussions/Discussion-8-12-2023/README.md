# React Routing

---
###### Student: John Keen
###### Professor: Bobby Estey
###### Assignment: Component Rendering
###### Date: 8/12/2023

---

---
### React Routing

This is the BrowserRouter I used in the web application I created for the milestone of the class Advanced JavaScript.

Each component is like a page in the web application.  


#### App.js

```jsx
<BrowserRouter>
    <NavBar manageLoggedIn={managerLoggedIn}></NavBar>
    <Routes>
        <Route exact path="/" element={<About />} />
        <Route exact path="/about" element={<About />} />
        <Route exact path="/shop" element={<Shop onSubmit={updateSearchResults} addToCart={addToMyCart} basket={renderedList} />} />
        <Route exact path="/shop/:searchTerm" element={<Shop onSubmit={updateSearchResults} addToCart={addToMyCart} basket={renderedList}/>} />
        <Route exact path="/ShoppingCart" element={<ShoppingCart onSubmit={updateSearchResults} removeFromCart={removeFromMyCart} basket={myCart}/>} />
        <Route exact path="/login" element={<Login updateManage={updateManagerLoggedIn}/>} />
        <Route exact path="/register" element={<Register />} />
        <Route exact path="/manage" element={<Manage onSubmit={updateSearchResults} basket={renderedList} reload={loadProducts}/>} />
    </Routes>
</BrowserRouter>
```

---
