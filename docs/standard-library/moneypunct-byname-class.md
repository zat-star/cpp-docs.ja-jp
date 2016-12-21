---
title: "moneypunct_byname クラス | Microsoft Docs"
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
  - "std.moneypunct_byname"
  - "std::moneypunct_byname"
  - "xlocmon/std::moneypunct_byname"
  - "moneypunct_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "moneypunct_byname クラス"
ms.assetid: e8a544d2-6aee-420d-b513-deb385c9b416
caps.latest.revision: 22
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# moneypunct_byname クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

特定のロケールの `moneypunct` のファセットとして使用できるオブジェクトを表す派生テンプレート クラス通貨書式入力金融出力フィールドを有効にします。  
  
## 構文  
  
```  
template<class CharType, bool Intl = false>  
class moneypunct_byname : public moneypunct<CharType, Intl>  
{  
public:  
    explicit moneypunct_byname(  
        const char *_Locname,  
        size_t _Refs = 0  
    );  
    explicit moneypunct_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );   
protected:  
    virtual ~moneypunct_byname();  
};  
```  
  
## 解説  
 この動作は名前付きなロケール `_Locname`によって決まります。  各コンストラクターは [moneypunct](../Topic/moneypunct::moneypunct.md)\<CharType、Intl\> \(`_Refs`\) の基本オブジェクトを初期化します。  
  
## 必要条件  
 **ヘッダー:** の \<ロケール\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)