# Minecraft JNI Exploration & Reverse Engineering

## 🎯 **Project Overview**

This repository documents the process of me attempting reverse engineering Minecraft's obfuscated Java classes through JNI reflection, with a focus on discovering method signatures and accessing game state from native code.

### **Target Version**
- **Minecraft**: 1.16.1
- **Mappings**: Obfuscated
- **JNI**: Native C++ DLL injection
- **Platform**: Windows

## 🔍 **Key Discoveries**

### **Minecraft Class Hierarchy (1.16.1)**
```
dlx (Minecraft Main Class)
  └── Z() method → aom (Entity/Player Class)
      └── ??? method → beb (Inventory Class)
          └── Fields: items array, selected slot, etc.
```

## 📊 **What Works**
1. **JNI Reflection**: Using `getDeclaredMethods()` and `getDeclaredFields()`
2. **Player Data Access**: Position, rotation, boolean states work perfectly
3. **Method Discovery**: Successfully found `dlx.Z()` → `aom` player method
4. **Field Access**: Direct field access using obfuscated names (cc, cd, ce, cf, cg)
5. **Class Finding**: `env->FindClass()` works for obfuscated names

## 📚 **References**

- [JNI Specification](https://docs.oracle.com/javase/8/docs/technotes/guides/jni/)
- [Minecraft Obfuscation Mappings](https://github.com/FabricMC/yarn)
- [Java Reflection Documentation](https://docs.oracle.com/javase/tutorial/reflect/)

---

**Status**: Active Development | **Last Updated**: September 2025
**Contributors**: AI Assistant + Human Researcher
