# 08 — System Design & Architecture

[← Learning index](../README.md)

## System design
Business requirements ko services, data storage, APIs, scaling, security aur failure handling mein translate karna system design hai. Pehle functional aur non-functional requirements clear karo.

Example: food delivery system mein customer, restaurant, order, payment aur delivery workflows plan karne hote hain.

## Scalability
Vertical scaling machine ko zyada CPU/RAM dena hai. Horizontal scaling multiple instances add karna hai. Stateless services horizontal scale karna comparatively easy ho sakta hai; database bottlenecks alag solve karne padte hain.

## Load balancing
Load balancer requests ko healthy server instances mein distribute karta hai. Health checks, timeouts, retries aur session behavior design karna hota hai. Example: 3 web servers ke peeche load balancer; unhealthy server ko traffic na mile.

## Monolith vs microservices
Monolith ek deployable application hai; small systems ke liye simpler ho sakta hai. Microservices independently deployable services hoti hain, lekin network failures, observability, data consistency aur operations complexity badhati hain. Microservices automatically better nahi hain.

## Multi-tenant systems
Ek application multiple organizations/customers serve karti hai. Tenant isolation, authorization, data partitioning, configuration aur billing carefully design karo. Example: HR SaaS mein Company A ka user Company B ke employee records access na kar sake.

## Caching, queues and CDN
Cache repeated reads fast kar sakta hai. Queue background jobs ko decouple karti hai. CDN static content users ke paas deliver karta hai. Failure modes aur stale data behavior define karo.

## Architecture trade-offs
Cost vs latency, consistency vs availability aur simplicity vs flexibility trade-offs hain. Workload measure karo; bottleneck prove hone se pehle unnecessary complexity add mat karo.

## Practice
1. Vertical aur horizontal scaling compare karo.
2. Multi-tenant data isolation ke 3 controls batao.
3. Startup ke liye monolith kab sensible ho sakta hai?