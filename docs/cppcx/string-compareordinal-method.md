---
title: "String::CompareOrdinal メソッド | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::CompareOrdinal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::CompareOrdinal"
ms.assetid: dd4a7acc-fd23-4f1e-af85-64b9086f63f8
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::CompareOrdinal メソッド
オブジェクトによって表される 2 つの文字列値に含まれる、対応する文字列の数値を評価することにより、2 つの `String` オブジェクトを比較します。  
  
## 構文  
  
```cpp  
  
int CompareOrdinal(  
           String^ str1,   
           String^ str2)  
  
```  
  
#### パラメーター  
 `str1`  
 1 つ目の String オブジェクト。  
  
 `str2`  
 2 つ目の String オブジェクト。  
  
## 戻り値  
 2 つの比較対照値の構文上の関係を示す整数。 次の表は、可能性のある戻り値の一覧です。  
  
|値|条件|  
|-------|--------|  
|\-1|`str1` は `str2` より小さい値です。|  
|0|`str1` は `str2` と等価。|  
|1|`str1` が `str2` より大きくなっています。|  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** vccorlib.h  
  
## 参照  
 [Platform::String クラス](../cppcx/platform-string-class.md)