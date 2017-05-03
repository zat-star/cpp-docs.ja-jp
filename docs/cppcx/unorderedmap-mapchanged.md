---
title: "UnorderedMap::MapChanged | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::MapChanged"
ms.assetid: 6863781e-35af-4e77-9a11-277bd00f5d41
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# UnorderedMap::MapChanged
項目がマップに挿入されたときまたはマップから削除されたときに発生します。  
  
## 構文  
  
```cpp  
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;  
```  
  
## プロパティ値\/戻り値  
 イベントを発生させたオブジェクト、および発生した変更の種類に関する情報を含む [MapChangedEventHandler\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br206644.aspx)。 「[IMapChangedEventArgs\<K\>](http://msdn.microsoft.com/library/windows/apps/br226034.aspx)」および「[CollectionChange 列挙](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx)」も参照してください。  
  
## 同等の .NET Framework 関数  
 C\# または Visual Basic プロジェクト IMap\<K,V\> を IDictionary\<K,V\> として使用する Windows ストア アプリ。  
  
## 必要条件  
 Windows 8.0 以上  
  
## 参照  
 [コレクション](../cppcx/collections-c-cx.md)