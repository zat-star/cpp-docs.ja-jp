---
title: "time_get_byname クラス | Microsoft Docs"
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
  - "std.time_get_byname"
  - "time_get_byname"
  - "xloctime/std::time_get_byname"
  - "std::time_get_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_get_byname クラス"
ms.assetid: 6e54153e-da40-4bb9-a942-1a6ce57b30c9
caps.latest.revision: 25
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# time_get_byname クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

派生テンプレート クラスは、型 `time_get`\<CharType、InputIterator\>のロケールのファセットとして使用できるオブジェクトを表します。  
  
## 構文  
  
```  
template<class Elem, class InputIterator =   
   istreambuf_iterator<CharType, char_traits<CharType> > >  
   class time_get_byname : public time_get<CharType, InputIterator>  
{  
public:  
    explicit time_get_byname(  
        const char *_Locname,  
         size_t _Refs = 0  
    );  
    explicit time_get_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );  
protected:  
    virtual ~time_get_byname()  
};  
```  
  
#### パラメーター  
 `_Locname`  
 名前付きなロケール。  
  
 `_Refs`  
 参照カウントの初期値。  
  
## 必要条件  
 この動作は名前付きなロケール `_Locname`によって決まります。  各コンストラクターは [time\_get](../Topic/time_get::time_get.md)\<CharType、InputIterator\> \(`_Refs`\) の基本オブジェクトを初期化します。  
  
## 必要条件  
 **ヘッダー:** の \<ロケール\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)