---
title: "numpunct_byname クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.numpunct_byname"
  - "numpunct_byname"
  - "xlocnum/std::numpunct_byname"
  - "std::numpunct_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numpunct_byname クラス"
ms.assetid: 18412924-e085-4771-b5e9-7a200cbdd7c0
caps.latest.revision: 24
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# numpunct_byname クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

派生テンプレート クラスの特定のロケールの `numpunct` のファセットとして使用できるオブジェクトを説明します。数値型と Boolean 式の書式設定および区切りを有効にします。  
  
## 構文  
  
```  
template<Class CharType>  
    class numpunct_byname : public numpunct<Elem> {  
public:  
    explicit numpunct_byname(  
        const char* _Locname,  
        size_t _Refs = 0  
    );  
    explicit numpunct_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );  
protected:  
    virtual ~numpunct_byname( );  
   };  
```  
  
## 解説  
 この動作は [名前付き](../Topic/locale::name.md) のロケール `_Locname`によって決まります。  コンストラクターは [numpunct](../Topic/numpunct::numpunct.md)\<CharType\> \(`_Refs`\) の基本オブジェクトを初期化します。  
  
## 必要条件  
 **ヘッダー:** の \<ロケール\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)