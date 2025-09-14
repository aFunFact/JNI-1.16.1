# Minecraft JNI Exploration & Reverse Engineering

## 🎯 **Project Overview**

This repository documents the process of me attempting to reverse engineer Minecraft's obfuscated Java classes, with a focus on discovering method signatures and accessing/manipulating game state from native code.

### **Target Version**
- **Minecraft**: 1.16.1
- **Mappings**: Obfuscated
- **JNI**: Native C++ DLL injection
- **Platform**: Windows

### **Minecraft Class Hierarchy (1.16.1)**
```
  (dlx) this is minecraft's obfuscated class name, assign to a jclass
    └── (B) capital B is important here, B is obfuscated to getInstance(), assign to a jmethodID, Minecraft is a singleton architecture, everything is passed through one instance/here
      └── Z() method → aom (Entity base class)
```

## 📊 **Reverse engineering techniques used**
1. **JNI Reflection**: 
2. **Method Structure Indicators**: e.g. getInstance is a static method, can call without creating an instance, no parameters, typical singleton pattern

## **Where I'm stuck**
1. **JNI method signatures**: e.g. Z()
   
## 📚 **References**

- [JNI Specification](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/)
- [Minecraft Obfuscation Mappings](https://piston-data.mojang.com/v1/objects/ddf517a4f6750f4c15189de4e03246ae1f916cf5/client.txt)
- [Java Reflection Documentation](https://docs.oracle.com/javase/tutorial/reflect/)

---

**Status**: Active Development | **Last Updated**: September 2025
