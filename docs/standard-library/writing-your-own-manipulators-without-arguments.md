---
title: "引数を使用しない独自マニピュレーターの作成 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "マニピュレーター"
ms.assetid: 2dc62d09-45b7-454d-bd9d-55f3c72c206d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 引数を使用しない独自マニピュレーターの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

引数を使用しない書き込みのマニピュレーターは複雑なマクロ クラスの派生が使用は必要ではありません。  プリンターが Esc キー ペア \<を必要とするとします。\[\>太字モードを適用します。  ストリームにこのペアを挿入する:  
  
```  
cout << "regular " << '\033' << '[' << "boldface" << endl;  
```  
  
 または文字を挿入する `bold` のマニピュレーターを定義する:  
  
```  
ostream& bold( ostream& os ) {  
    return os << '\033' << '[';  
}  
cout << "regular " << bold << "boldface" << endl;  
```  
  
 `bold` のグローバルに定義された関数は `ostream` の参照引数を受け取り、`ostream` の参照を返します。  、プライベート クラスの要素にアクセスする必要がないため、メンバー関数または Friend ではありません。  `bold` 関数はストリームに次のような表示宣言を使用する関数の型、ことを受け入れるようにストリームの `<<` の演算子がオーバーロードされるために接続します:  
  
```  
_Myt& operator<<(ios_base& (__cdecl *_Pfn)(ios_base&))  
{     
   // call ios_base manipulator  
   (*_Pfn)(*(ios_base *)this);  
   return (*this);  
}  
```  
  
 他のオーバーロードされた演算子を拡張するには、この機能を使用できます。  この場合、`bold` をストリームに文字を挿入すること付帯的です。  関数は、隣接する文字を印刷するときにストリームに挿入すると、必ず呼び出されます。  したがって、出力は、ストリームのバッファリングに低下する可能性があります。  
  
## 参照  
 [出力ストリーム](../standard-library/output-streams.md)