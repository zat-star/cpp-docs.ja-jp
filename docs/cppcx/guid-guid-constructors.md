---
title: "Guid::Guid コンストラクター | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Guid::Guid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "プラットフォーム、Guid::Guid"
  - "Guid::Guid"
ms.assetid: dfa4dcad-1c3b-481f-9f60-05141b9788d1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Guid::Guid コンストラクター
Guid 構造体の新しいインスタンスを初期化します。  
  
## 構文  
  
```cpp  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        unsigned char d,   
        unsigned char e,   
        unsigned char f,   
        unsigned char g,   
        unsigned char h,   
        unsigned char i,   
        unsigned char j,   
        unsigned char k  
);  
  
    Guid(   
        GUID m  
);  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        Array<unsigned char>^ n  
);  
```  
  
#### パラメーター  
 `a`  
 GUID の最初の 4 バイト。  
  
 `b`  
 GUID の次の 2 バイト。  
  
 `c`  
 GUID の次の 2 バイト。  
  
 `d`  
 GUID の次のバイト。  
  
 `e`  
 GUID の次のバイト。  
  
 `f`  
 GUID の次のバイト。  
  
 `g`  
 GUID の次のバイト。  
  
 `h`  
 GUID の次のバイト。  
  
 `i`  
 GUID の次のバイト。  
  
 `j`  
 GUID の次のバイト。  
  
 `k`  
 GUID の次のバイト。  
  
 `m`  
 定義されたとおりの GUID。  
  
 `n`  
 GUID の残りの 8 バイト。  
  
## 必要条件  
 **サポートされている最低限のクライアント:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **サポートされている最低限のサーバー:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **名前空間:** Platform  
  
 **メタデータ:** platform.winmd  
  
## 参照  
 [Platform::Guid 値クラス](../cppcx/platform-guid-value-class.md)