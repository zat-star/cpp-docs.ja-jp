---
title: "messages_byname クラス | Microsoft Docs"
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
  - "messages_byname"
  - "std::messages_byname"
  - "std.messages_byname"
  - "xlocmes/std::messages_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "messages_byname クラス"
ms.assetid: c6c64841-3e80-43c8-b54c-fed41833ad6b
caps.latest.revision: 22
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# messages_byname クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

派生テンプレート クラスの特定のロケールのメッセージのファセットとして使用できるオブジェクトを説明します。ローカライズされたメッセージ検索を有効にします。  
  
## 構文  
  
```  
template<class CharType>  
    class messages_byname : public messages<CharType> {  
public:  
    explicit messages_byname(  
        const char *_Locname,  
        size_t _Refs = 0  
    );  
    explicit messages_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );   
protected:  
    virtual ~messages_byname();  
};  
```  
  
#### パラメーター  
 `_Locname`  
 名前付きなロケール。  
  
 `_Refs`  
 参照カウントの初期値。  
  
## 解説  
 この動作は名前付きなロケール `_Locname`によって決まります。  各コンストラクターは [メッセージ](../Topic/messages::messages.md)\<CharType\> \(`_Refs`\) の基本オブジェクトを初期化します。  
  
## 必要条件  
 **ヘッダー:** の \<ロケール\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)