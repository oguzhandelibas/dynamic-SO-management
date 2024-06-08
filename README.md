# ScriptableObject Management for Unity

This project provides a ScriptableObjectManager class for easily managing ScriptableObjects in Unity. This static helper class can be used to load and cache ScriptableObjects efficiently.

# Features
- ScriptableObject Loading: Seamlessly loads ScriptableObjects from predefined paths.
- Caching: Efficiently caches loaded ScriptableObjects for quick access, reducing load times and improving performance.
- Enum-Based Management: Utilizes an enumeration to manage different ScriptableObject types, ensuring type safety and easy maintenance.

# Usage

## ScriptableObject Types
Define the ScriptableObject types you support using an enumeration. This project includes a sample enum called ScriptableObjectType.

## ScriptableObjectManager Class
The ScriptableObjectManager class provides static methods for loading and caching ScriptableObjects.

## LoadScriptableObject<T>(): Generic method to load and cache the specified type of ScriptableObject. If the ScriptableObject has been previously loaded, it returns the cached instance.
GetScriptableObjectType<T>(): Helper method to map the generic type to the corresponding enum value.

