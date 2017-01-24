---
title: "1 段階でのオブジェクトの構築と 2 段階でのオブジェクトの構築 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "オブジェクト作成, グラフィック オブジェクト"
  - "オブジェクト [C++], 作成 (グラフィック オブジェクトを)"
  - "オブジェクト [C++], グラフィック オブジェクト"
  - "1 段階でのオブジェクトの構築と 2 段階でのオブジェクトの構築"
ms.assetid: 5a1c410c-4a4b-4dd9-a2ec-ced831aa7f21
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1 段階でのオブジェクトの構築と 2 段階でのオブジェクトの構築
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ペンとブラシなどのグラフィック オブジェクトを作成するための 2 種類の方法選ぶ必要があります:  
  
-   *二つの構築*:一段 1 段階の、コンストラクターですべてオブジェクトを構築し、初期化してください。  
  
-   *正常な式構築*: 2 種類の段階オブジェクトを構築し、初期化してください。  コンストラクターはオブジェクトを作成し、初期化関数を初期化します。  
  
 正常な構築式は、常に安全です。  二つ目の一段の構築では、コンストラクターは不適切な引数を指定するか、メモリの割り当てに失敗した場合には例外をスローしてしまう可能性があります。  この問題は、正常な更新構築してエラーをチェックする必要があるが、回避できます。  いずれの場合も、オブジェクトを破棄すると、同じプロセスです。  
  
> [!NOTE]
>  これらの手法は、オブジェクト、グラフィック オブジェクトではなく、クエリの作成に適用されます。  
  
## 両方の構築の例  
 次の簡単な例で、ペンのオブジェクトを構築する二つのメソッドを示します。:  
  
 [!code-cpp[NVC_MFCDocViewSDI#6](../mfc/codesnippet/CPP/one-stage-and-two-stage-construction-of-objects_1.cpp)]  
  
### さらに詳しくは次のトピックをクリックしてください  
  
-   [グラフィック オブジェクト](../mfc/graphic-objects.md)  
  
-   [デバイス コンテキストへのグラフィック オブジェクトの選択](../mfc/selecting-a-graphic-object-into-a-device-context.md)  
  
-   [デバイス コンテキスト](../Topic/Device%20Contexts.md)  
  
-   [ビューで描画できます。](../mfc/drawing-in-a-view.md)  
  
## 参照  
 [グラフィック オブジェクト](../mfc/graphic-objects.md)