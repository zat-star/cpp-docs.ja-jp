---
title: "messages クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "messages"
  - "xlocmes/std::messages"
  - "std.messages"
  - "std::messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "messages クラス"
ms.assetid: c4c71f40-4f24-48ab-9f7c-daccd8d5bd83
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# messages クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このテンプレート クラスは、特定のロケールの国際化メッセージのカタログからローカライズされたメッセージを取得するためにロケールのファセットとして使用できるオブジェクトを表します。  
  
 現在、messages クラスは実装されていますが、メッセージはありません。  
  
## 構文  
  
```  
template <class CharType>  
   class messages : public messages_base;  
```  
  
#### パラメーター  
 `CharType`  
 ロケールの文字をエンコードするためにプログラム内で使用される型。  
  
## 解説  
 すべてのロケールのファセットと同様、静的オブジェクト ID に最初に格納されている値は 0 です。 一意な正の値を格納する、格納されている値にアクセスする最初の試行 **id**。  
  
 このファセットは基本的に基底クラスの messages\_base で定義されているメッセージのカタログを開き、必要な情報を取得し、カタログを閉じます。  
  
### コンストラクター  
  
|||  
|-|-|  
|[メッセージ](../Topic/messages::messages.md)|メッセージのファセット コンストラクター関数。|  
  
### Typedefs  
  
|||  
|-|-|  
|[char\_type](../Topic/messages::char_type.md)|メッセージを表示するために使用される文字型。|  
|[string\_type](../Topic/messages::string_type.md)|`basic_string` 型の文字を格納する `CharType` 型の文字列を表す型。|  
  
### メンバー関数  
  
|||  
|-|-|  
|[閉じる](../Topic/messages::close.md)|メッセージ カタログを閉じます。|  
|[do\_close](../Topic/messages::do_close.md)|メッセージ カタログを閉じるために呼び出される仮想関数。|  
|[do\_get](../Topic/messages::do_get.md)|メッセージ カタログを取得するために呼び出される仮想関数。|  
|[do\_open](../Topic/messages::do_open.md)|メッセージ カタログを開くために呼び出される仮想関数。|  
|[取得](../Topic/messages::get.md)|メッセージ カタログを取得します。|  
|[開く](../Topic/messages::open.md)|メッセージ カタログを開きます。|  
  
## 必要条件  
 **ヘッダー:** \<locale\>  
  
 **名前空間:** std  
  
## 参照  
 [\<locale\>](../standard-library/locale.md)   
 [messages\_base クラス](../Topic/messages_base%20Class.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)