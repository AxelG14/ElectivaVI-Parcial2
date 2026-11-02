# 📄 Analizador de Documentos — Sistema RAG Avanzado

> **Inteligencia Artificial Generativa y Sistemas Inteligentes**  
> **Institución Universitaria EAM — 2026-II**  
> **Profesor:** Robert Garcia Rey  

---

## 👥 1. Identificación del Equipo

| Integrantes | 
|---|---|---|
| Axel Gutierrez | 
| Pablo Garces | 

* **Equipo:** `Equipo_Analizador`
* **Corte:** Segundo Corte (Evaluación y Mejora de RAG)

---

## 🎯 2. Descripción del Problema y Objetivo

### 📌 El Problema
En la gestión documental corporativa (procesamiento de facturas, contratos de prestación de servicios y verificación de identificaciones), las consultas operativas suelen ser propensas a errores de interpretación normativa o requieren revisión manual exhaustiva. Los modelos de lenguaje (LLM) convencionales utilizados sin contexto adecuado tienden a **alucinar** requisitos, plazos o estados dinámicos que no corresponden a la reglamentación vigente.

### 💡 La Solución
Se construyó un **Sistema de Generación Aumentada por Recuperación (RAG)** avanzado. El sistema ingiere la normativa interna (`politicas_facturacion.md` y `gestion_contratos_identificacion.md`), persiste sus embeddings en una base de datos remota en **Supabase Vector**, y ejecuta un pipeline de recuperación híbrida (búsqueda semántica + BM25 + fusión RRF + reordenamiento por Cross-Encoder). Finalmente, genera respuestas estructuradas, citadas e inmutables validadas mediante **Pydantic** a través de la API de **Groq**.

---

## 🏗️ 3. Arquitectura del Sistema

El pipeline se divide en 4 etapas principales:
