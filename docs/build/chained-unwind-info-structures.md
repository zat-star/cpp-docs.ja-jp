---
title: "チェーン アンワインド情報の構造 | Microsoft Docs"
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
ms.assetid: 176835bf-f118-45d9-9128-9db4b7571864
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# チェーン アンワインド情報の構造
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

UNW\_FLAG\_CHAININFO フラグを設定している場合、アンワインド情報構造は二次的な情報になり、共有例外ハンドラーまたはチェーン情報アドレス フィールドに基本アンワインド情報が含まれます。  次に示すコードは、`unwindInfo` が UNW\_FLAG\_CHAININFO フラグを設定した構造体であると想定して、基本アンワインド情報を取得します。  
  
```  
PRUNTIME_FUNCTION primaryUwindInfo = (PRUNTIME_FUNCTION)&(unwindInfo->UnwindCode[( unwindInfo->CountOfCodes + 1 ) & ~1]);  
```  
  
 チェーン情報は、次の 2 つのシナリオで役立ちます。  1 つは、非連続のコード セグメントで使用する場合です。  チェーン情報を使用すると、基本アンワインド情報からアンワインド コード配列を複製する必要がないため、必要なアンワインド情報のサイズを削減できます。  
  
 もう 1 つは、揮発性レジスタの保存をグループ化するためにチェーン情報を使用する場合です。  コンパイラが、関数のエントリのプロローグの範囲の外側まで、揮発性レジスタの保存を遅延するように設定する場合があります。  これを記録するには、グループ化されたコードの前に関数部分の基本アンワインド情報を置き、次に 0 以外のサイズのプロローグを持つチェーン情報を設定します。この場合、チェーン情報のアンワインド コードは、不揮発性レジスタの保存を反映します。  その場合には、アンワインド コードは、すべて UWOP\_SAVE\_NONVOL のインスタンスになります。  PUSH を使用して保存したり、追加の固定スタック割り当てを使用して RSP の登録を不揮発性レジスタを変更するグループはサポートされていません。  
  
 UNW\_FLAG\_CHAININFO セットを持つ UNWIND\_INFO 項目が、その UNWIND\_INFO 項目にも UNW\_FLAG\_CHAININFO セットがある RUNTIME\_FUNCTION エントリを指すことができます \(複数シュリンクラッピング\)。  最終的に、チェーン アンワイド情報ポインターをたどると、UNW\_FLAG\_CHAININFO がクリアされた UNWIND\_INFO 項目に到達します。この項目は、実際のプロシージャのエントリ ポイントを指す基本 UNWIND\_INFO 項目です。  
  
## 参照  
 [例外処理とデバッガー サポートのためのアンワインド データ](../build/unwind-data-for-exception-handling-debugger-support.md)