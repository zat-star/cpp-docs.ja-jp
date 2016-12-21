---
title: "SEGMENT | Microsoft Docs"
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
  - "SEGMENT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SEGMENT directive"
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# SEGMENT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

セグメント属性を持つ  *という名前*  プログラムセグメントを定義します。  
  
## 構文  
  
```  
  
   name SEGMENT [[READONLY]] [[align]] [[combine]] [[use]] [[characteristics]] ALIAS(string) [['class']]  
statements  
name ENDS  
```  
  
#### パラメーター  
 *配置します。*  
 セグメントの開始アドレスを選択できるメモリ アドレスの範囲。  配置の種類は次のいずれかです :  
  
|型を配置します。|の開始アドレス|  
|--------------|-------------|  
|**BYTE**|次のバイトアドレス。|  
|**WORD**|次に使用できるアドレス \(ワードあたり 2 バイト\)。|  
|**DWORD**|次の二つのアドレス \(ダブル ワードあたり 4 バイト\)。|  
|**パラグラフ**|次の段落のアドレス \(段落ごとに 16 バイト\)。|  
|**PAGE**|次に使用できるページ アドレス \(ページごとに 256 バイト\)。|  
|**整列** \(n\)|次の *N 番目*  バイトアドレス。  詳細については" 解説 " を参照してください。|  
  
 このパラメーターを指定しなかった場合 **パラグラフ**  が既定で使用されます。  
  
 *結合*  
 **パブリック   スタック   共通   メモリ**  のの  *アドレス*  **プライベート**  
  
 *使用*  
 **USE16 USE32  フラット**  
  
 `characteristics`  
 **情報   読み取り   書き込み   実行   共有  NOPAGE NOCACHE** と  **破棄**  
  
 これらはどちらの場合にのみサポートされ似た名前の COFF セクションの特性に対応します \(たとえば **共有**  は IMAGE\_SCN\_MEM\_SHARED に対応します。  設定を IMAGE\_SCN\_MEM\_READ フラグ参照してください。  旧式の読み取り専用フラグによりセクションでは IMG\_SCN\_MEM\_WRITE のフラグをクリアします。  どの `characteristics``characteristics` 設定されている場合既定の特性は使用されずプログラマ指定されたフラグだけ有効です。  
  
 `ALIAS(` `string` `)`  
 この文字列は二つの COFF オブジェクトのセクション名として使用されます。  個々の MASM セグメント名は同じ外部名の複数のセクションを作成します。  
  
 **\/omf** でサポートされていません。  
  
 `class`  
 セグメントがどのように実行されたファイルにまとめられ並べ替え方法を指定します。  一般的な値は`'DATA'``'CODE'``'CONST'` と `'STACK'` あります。  
  
## 解説  
 `ALIGN(` `n` `)` `n` に 2 1 ~ 8192 の累乗でもそのまま ; **\/omf** でサポートされていません。  
  
## 参照  
 [Directives Reference](../../assembler/masm/directives-reference.md)