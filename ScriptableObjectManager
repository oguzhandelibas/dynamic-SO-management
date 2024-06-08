using System;
using System.Collections.Generic;
using UnityEngine;

public static class ScriptableObjectManager
{
    private static readonly Dictionary<ScriptableObjectType, string> Paths = new Dictionary<ScriptableObjectType, string>
    {
        { ScriptableObjectType.GameSignals, "GameSignals"},
    };

    private static readonly Dictionary<ScriptableObjectType, ScriptableObject> _cache = new Dictionary<ScriptableObjectType, ScriptableObject>();

    public static T LoadScriptableObject<T>() where T : ScriptableObject
    {
        var type = GetScriptableObjectType<T>();
        return LoadScriptableObject<T>(type);
    }
    
    private static T LoadScriptableObject<T>(ScriptableObjectType type) where T : ScriptableObject
    {
        if (_cache.TryGetValue(type, out var value))
        {
            return value as T;
        }

        if (Paths.TryGetValue(type, out string path))
        {
            T scriptableObject = Resources.Load<T>(path);
            if (scriptableObject != null)
            {
                _cache[type] = scriptableObject;
                return scriptableObject;
            }
            else
            {
                Debug.LogError($"ScriptableObject of type {type} at path {path} could not be loaded.");
            }
        }
        else
        {
            Debug.LogError($"Path for ScriptableObject of type {type} not found.");
        }

        return null;
    }

    private static ScriptableObjectType GetScriptableObjectType<T>() where T : ScriptableObject
    {
        if (typeof(T) == typeof(GameSignals))
            return ScriptableObjectType.GameSignals;
        
        throw new ArgumentException($"Unsupported ScriptableObject type: {typeof(T)}");
    }
}
