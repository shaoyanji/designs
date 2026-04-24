# Caching Design

## Overview

This document outlines caching strategies for improving application performance.

## Cache Layers

### Browser Cache
- HTTP cache headers (Cache-Control, ETag)
- Service Worker for offline support
- LocalStorage/IndexedDB for user preferences

### CDN Cache
- Static assets cached at edge
- Cache TTL based on file type
- Purge strategies for deployment

### Application Cache
- In-memory (Redis, Memcached)
- Response caching
- Database query caching

## Cache Patterns

### Cache-Aside (Lazy Loading)
1. Check cache first
2. If miss, fetch from source
3. Store in cache
4. Return data

### Write-Through
1. Write to cache and source simultaneously
2. Simpler but higher latency

### Write-Behind (Async)
1. Write to cache immediately
2. Async write to source
- Higher throughput, risk of data loss

## Cache Invalidation

### Strategies
| Strategy | When to Use |
|----------|-------------|
| TTL (Time To Live) | Predictable data freshness |
| Explicit deletion | Specific events trigger invalidation |
| Versioned keys | New version = new key |

### Hard Problems
- Cache stampede: Use probabilistic early expiration
- Thundering herd: Implement request coalescing

## Redis Configuration

### Data Structures
- Strings: Simple key-value
- Hashes: Objects with multiple fields
- Lists: Queues, timelines
- Sets: Unique collections, tags
- Sorted Sets: Leaderboards, time-series

### Eviction Policies
- `allkeys-lru` - Evict least recently used
- `volatile-lru` - Evict expiring keys, LRU
- `allkeys-random` - Random eviction
- `noeviction` - Return errors when full

## Cache Keys

Naming convention: `service:entity:id:field`

Examples:
- `user:123:profile`
- `post:456:comments:page:1`
- `config:feature_flags`
