---
title: "2.7.2.5 default | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: c856df07-705c-4ad3-9105-a268dd33e939
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.5 default
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**既定**  の句はユーザーが変数のデータの共有の属性に影響を与えることができます。   **既定**  句の構文は次のとおりです。:  
  
```  
default(shared | none)  
```  
  
 **既定値 \(共有\)** を指定するには修飾される **threadprivate** または **Cons**`t`\- 場合明示的に  **共有**  の句の現在表示されている変数をリストと同じです。   **既定**  の明示的な句がない場合既定では  **既定値 \(共有\)** を指定した場合と同じです。  
  
 **既定値 \(なし\)** を指定するには次のうちいずれかの parallel コンストラクトの構文の範囲変数への参照にもなる必要がある必要があります :  
  
-   変数が参照を含む構造体のデータの共有の属性の句で明示的に表示されます。  
  
-   変数はparallel コンストラクトで宣言されます。  
  
-   変数は **threadprivate** です。  
  
-   変数に  **定数** \- 修飾型はになります。  
  
-   変数は**For** または  **並列の**  のディレクティブの後に変数がループの中に表示されます **For** のループのループ制御変数です。  
  
 変数をクロージャ ディレクティブの **lastprivate** により **firstprivate** で指定するか **リダクション**  の句は外側のコンテキストで変数への暗黙的な参照が発生します。  これらの暗黙的な参照は上記の要件に応じてあります。  
  
 **既定**  の一つの句だけ  **並列**  のディレクティブで指定される場合があります。  
  
 変数の既定のデータの共有の属性は  **プライベート firstprivatelastprivate リダクション** 次の例に示すように  **共有**  の句を使用してオーバーライドできます :  
  
```  
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\  
   private(x)  private(r)  lastprivate(i)  
```