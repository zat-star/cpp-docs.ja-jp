---
title: "time_put_byname クラス | Microsoft Docs"
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
  - "time_put_byname"
  - "xloctime/std::time_put_byname"
  - "std.time_put_byname"
  - "std::time_put_byname"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_put_byname クラス"
ms.assetid: e08c2348-64d2-4ace-98b1-1496e14c7b1a
caps.latest.revision: 25
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# time_put_byname クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

派生テンプレート クラス型のロケール ファセットとして使用できるオブジェクトを表します `time_put`\< CharType、OutputIterator \> です。  
  
## 構文  
  
```  
template<class CharType,  
 class OutIt = ostreambuf_iterator<CharType, char_traits<CharType> > >  
 class time_put_byname : public time_put<CharType, OutputIterator>  
{  
public:  
    explicit time_put_byname(  
        const char *_Locname,  
        size_t _Refs = 0  
    );  
    explicit time_put_byname(  
        const string& _Locname,  
        size_t _Refs = 0  
    );  
protected:  
    virtual ~time_put_byname();  
};  
```  
  
#### パラメーター  
 `_Locname`  
 ロケール名。  
  
 `_Refs`  
 最初の参照の数。  
  
## 解説  
 動作が決まります、 [という](../Topic/locale::name.md) ロケール `_Locname`します。 各コンス トラクターは、その基本オブジェクトを初期化 [time\_put](../Topic/time_put::time_put.md)\< CharType、OutputIterator \> \(`_Refs`\)。  
  
## 必要条件  
 **ヘッダー:** \<locale\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)