# 05 — Databases, APIs & Integration

[← Learning index](../README.md)

## Database basics
Database data ko store, retrieve, update aur organize karta hai. Example: Members table mein member ID, name aur department ID ho sakte hain.

## SQL vs NoSQL
SQL relational tables aur structured queries ke liye common hai. NoSQL document, key-value, graph aur doosre data models support karta hai. Choice data structure, queries, scale aur consistency needs par depend karti hai.

## API kya hai?
API systems ke beech communication ka contract hai. Ye define karta hai kaun se inputs, outputs, permissions aur errors possible hain. Example: GET /products products list deta hai; POST /orders order create kar sakta hai.

## HTTP methods and status codes
- GET: read data.
- POST: create/action.
- PUT/PATCH: replace/update.
- DELETE: delete.
Common status codes: 200 success, 201 created, 400 invalid request, 401 unauthenticated, 403 forbidden, 404 not found, 500 server error. Exact behavior API documentation se confirm karo.

## Authentication vs authorization
Authentication identity verify karti hai. Authorization permissions decide karti hai. Login successful hona authentication hai; sirf HR manager ko salary records access dena authorization hai.

## Integrations and webhooks
Integration systems ko data/workflow share karne deti hai. Webhook event hone par doosre endpoint ko notification bhej sakta hai. Retries, duplicate events, signatures aur failures handle karo.

## Practice
1. API ko real-world example se samjhao.
2. 401 aur 403 mein difference batao.
3. Salary data ke liye authorization kyun critical hai?