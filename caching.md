# Caching

## Problem Statement

You have joined a new project that is experiencing performance and scalability issues. Your team lead has asked you to investigate different caching approaches and understand how they can improve application performance.

## 1. Caching Fundamentals
- What is caching?
- Why is caching needed?
- How does caching work?
- Cache hit vs Cache miss.

## 2. Types of Caching
- In-memory caching
- Database caching
- Application-level caching
- Distributed caching
- Browser caching
- CDN caching

## 3. Caching Strategies
- Cache-aside (Lazy Loading)
- Read-through
- Write-through
- Write-back (Write-behind)
- Write-around

## 4. Caching Technologies
- Redis
- Memcached
- Python `functools.lru_cache`
- FastAPI caching

## 5. Important Concepts
- TTL (Time to Live)
- Cache invalidation
- Cache eviction policies
  - LRU (Least Recently Used)
  - LFU (Least Frequently Used)
  - FIFO (First In, First Out)
- Cache consistency
- Cache stampede

## 6. Practical Implementation
1. Implement caching using Python dictionaries.
2. Implement LRU caching using `functools.lru_cache`.
3. Set up Redis using Docker.
4. Integrate Redis with FastAPI.
5. Compare API response times with and without caching.
6. Test caching with multiple concurrent requests.

## Objective

Understand how caching reduces database load, improves application response times, and helps applications handle more concurrent users.
