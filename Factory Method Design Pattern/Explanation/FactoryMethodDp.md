# Factory Method Design Pattern

## Overview

The Factory Method Design Pattern is a creational design pattern that resolves the issue of Simple Factory Design Pattern which does not follow the Open-Closed Principle.

## Problem Solved

The Simple Factory pattern violates the Open-Closed Principle because adding new types requires modifying the existing switch-case code in the factory. Factory Method solves this by using individual factories for each class.

## Core Concept

Instead of creating objects based on the type passed by client for switch-case, we create individual factory for each factory classes which implements the main factory class. This forces the new factory to override a create method. Each create method returns a common interface with common method for all new classes with different configuration.

## How It Works

1. **Common Factory Interface**: All factories implement a shared factory interface
2. **Individual Factories**: Each concrete class has its own dedicated factory
3. **Override Create Method**: Each factory must override the create method
4. **Common Product Interface**: All concrete classes implement a shared product interface

## Adding New Types

When a new class is added, we need:

1. **Simple class** that implements the common interface
2. **Factory class** implementing the main factory interface

This way, adding new classes doesn't require changing the existing code, which follows the Open-Closed Principle.

## Benefits

- **Open-Closed Principle Compliance**: New types can be added without modifying existing code
- **Polymorphism**: Client code works with interfaces, not concrete classes
- **Single Responsibility**: Each factory is responsible for creating only one type
- **Loose Coupling**: Client depends on abstractions, not concrete implementations

## Comparison: Simple Factory vs Factory Method

| Aspect             | Simple Factory                     | Factory Method                   |
| ------------------ | ---------------------------------- | -------------------------------- |
| **Structure**      | One factory with switch-case       | Multiple factories, one per type |
| **OCP Compliance** | ❌ Violates (modify existing code) | ✅ Follows (add new classes)     |
| **Complexity**     | Simple to understand               | More complex structure           |
| **Extensibility**  | Limited                            | Highly extensible                |
| **Use Case**       | Learning, simple apps              | Production systems               |

## When to Use Factory Method

- **Production Systems**: Where maintainability is crucial
- **Frequently Changing Requirements**: When new types are added regularly
- **Large Applications**: Where following SOLID principles is important


## Conclusion

Factory Method Design Pattern is a significant improvement over Simple Factory. It demonstrates how proper abstraction and polymorphism can solve real-world design problems while maintaining clean, extensible code that follows the Open-Closed Principle.
