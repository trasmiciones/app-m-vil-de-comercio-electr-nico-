# app-m-vil-de-comercio-electr-nico-
Aplicación móvil de comercio electrónico
import React, { useState } from "react";
import { BrowserRouter as Router, Route, Routes, Link } from "react-router-dom";
import Home from "./pages/Home";
import Catalogo from "./pages/Catalogo";
import Carrito from "./pages/Carrito";
import Registro from "./pages/Registro";
import Pago from "./pages/Pago";

function App() {
  return (
    <Router>
      <nav className="p-4 bg-blue-600 text-white flex justify-around">
        <Link to="/">Inicio</Link>
        <Link to="/catalogo">Catálogo</Link>
        <Link to="/carrito">Carrito</Link>
        <Link to="/registro">Registro</Link>
        <Link to="/pago">Pago</Link>
      </nav>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/catalogo" element={<Catalogo />} />
        <Route path="/carrito" element={<Carrito />} />
        <Route path="/registro" element={<Registro />} />
        <Route path="/pago" element={<Pago />} />
      </Routes>
    </Router>
  );
}

export default App;

// Home.js
export function Home() {
  return <h1 className="text-center text-2xl mt-4">Bienvenido a nuestra tienda</h1>;
}

// Catalogo.js
export function Catalogo() {
  const productos = [
    { id: 1, nombre: "Producto 1", precio: "$10" },
    { id: 2, nombre: "Producto 2", precio: "$20" }
  ];
  return (
    <div>
      <h1 className="text-center text-2xl mt-4">Catálogo de Productos</h1>
      <ul>
        {productos.map((producto) => (
          <li key={producto.id}>{producto.nombre} - {producto.precio}</li>
        ))}
      </ul>
    </div>
  );
}

// Carrito.js
export function Carrito() {
  return <h1 className="text-center text-2xl mt-4">Tu carrito de compras</h1>;
}

// Registro.js
export function Registro() {
  return <h1 className="text-center text-2xl mt-4">Registro de usuario</h1>;
}

// Pago.js
export function Pago() {
  return <h1 className="text-center text-2xl mt-4">Proceso de pago</h1>;
}
