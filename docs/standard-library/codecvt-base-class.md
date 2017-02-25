---
title: "codecvt_base クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "codecvt_base"
  - "xlocale/std::codecvt_base"
  - "std.codecvt_base"
  - "std::codecvt_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "codecvt_base クラス"
ms.assetid: 7e95c083-91b4-4b3f-8918-0d4ea244a040
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# codecvt_base クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

変換の結果を示すためにファセットのメンバー関数には戻り値の型を使用する参照される **結果**と列挙型を定義するために使用される codecvt クラスの基本クラスです。  
  
## 構文  
  
```  
class codecvt_base : public locale::facet {  
public:  
    enum result {ok, partial, error, noconv};  
    codecvt_base(  
        size_t _Refs = 0  
);  
    bool always_noconv() const;  
    int max_length() const;  
    int encoding() const;  
    ~codecvt_base()  
protected:  
    virtual bool do_always_noconv() const;  
    virtual int do_max_length() const;  
    virtual int do_encoding() const;  
};  
```  
  
## 解説  
 クラスは、テンプレート クラス [codecvt](../standard-library/codecvt-class.md)のすべての特殊化に共通列挙体について説明します。  列挙体の結果は [do\_in](../Topic/codecvt::do_in.md) または [do\_out](../Topic/codecvt::do_out.md)から有効な戻り値について説明します。:  
  
-   内部や外部の文字エンコーディングとの間で変換が成功した場合**ok**。  
  
-   ターゲットが成功するには変換に十分な大きさ**部分**。  
  
-   ソース シーケンスが不適格場合**エラー**。  
  
-   関数が変換を実行する**noconv**。  
  
## 必要条件  
 **ヘッダー:** の \<ロケール\>  
  
 **名前空間:** std  
  
## 参照  
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)