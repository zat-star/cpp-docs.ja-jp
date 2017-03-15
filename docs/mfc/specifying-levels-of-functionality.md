---
title: "継承機能のレベルの指定 | Microsoft Docs"
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
  - "CObject クラス, 追加 (派生クラスに機能を)"
  - "動的生成機能のサポート"
  - "レベル [C++]"
  - "レベル [C++], 機能 (CObject の)"
  - "ランタイム [C++], クラス情報"
  - "ランタイム クラス, 情報サポート"
  - "シリアル化 [C++], CObject"
ms.assetid: 562669ba-c858-4f66-b5f1-b3beeea4f486
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 継承機能のレベルの指定
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは [CObject](../Topic/CObject%20Class.md)機能に追加する方法を\-派生クラスの次のレベルについて説明します。:  
  
-   [ランタイム クラス情報](#_core_to_add_run.2d.time_class_information)  
  
-   [動的生成サポート](#_core_to_add_dynamic_creation_support)  
  
-   [シリアル化のサポート](#_core_to_add_serialization_support)  
  
 `CObject` の機能に関する一般的な説明については、"情報 [CObject からクラスを派生すること](../mfc/deriving-a-class-from-cobject.md)を参照してください。  
  
#### ランタイム クラス情報を追加します。  
  
1.  [CObject からクラスを派生すること](../mfc/deriving-a-class-from-cobject.md) の記事"に説明されているように、`CObject`からクラスを派生してください。  
  
2.  次に示すように、クラス宣言で `DECLARE_DYNAMIC` マクロを使用する:  
  
     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/CPP/specifying-levels-of-functionality_1.h)]  
  
3.  クラスの実装ファイル \(.cpp\) で `IMPLEMENT_DYNAMIC` マクロを使用します。  このマクロは、引数として、次のように、クラスが、基本クラスの名前を受け取って:  
  
     [!code-cpp[NVC_MFCCObjectSample#3](../mfc/codesnippet/CPP/specifying-levels-of-functionality_2.cpp)]  
  
> [!NOTE]
>  クラスの実装ファイル \(.cpp\) に `IMPLEMENT_DYNAMIC` を常に配置します。  したがって `IMPLEMENT_DYNAMIC` マクロは、コンパイル中に一度だけ評価され、インターフェイス ファイルには使用しないでください。複数のファイルに含めることができる H\)。  
  
#### 動的生成サポートを追加するには  
  
1.  `CObject`からクラスを派生してください。  
  
2.  クラス宣言で `DECLARE_DYNCREATE` マクロを使用します。  
  
3.  既定のコンストラクター \(引数を持たないコンストラクター\) を定義します。  
  
4.  クラスの実装ファイルに `IMPLEMENT_DYNCREATE` マクロを使用します。  
  
#### シリアル化のサポートを追加するには  
  
1.  `CObject`からクラスを派生してください。  
  
2.  `Serialize` のメンバー関数をオーバーライドします。  
  
    > [!NOTE]
    >  つまり、`Serialize` を直接呼び出す場合は省略して手順 3.から 5 をポリモーフィック ポインターを通じてオブジェクトをシリアル化するかどうか。  
  
3.  クラス宣言で `DECLARE_SERIAL` マクロを使用します。  
  
4.  既定のコンストラクター \(引数を持たないコンストラクター\) を定義します。  
  
5.  クラスの実装ファイルに `IMPLEMENT_SERIAL` マクロを使用します。  
  
> [!NOTE]
>  「ポインター」はポリモーフィック クラス \(呼び出す A からオブジェクトを派生クラスのオブジェクトを示す\) または指し示して \(B\) 通知します。  ポリモーフィック ポインターからシリアル化するには、フレームワークが基本クラス \(A\) から派生したクラスのオブジェクトである可能性があるため、\(b\) をシリアル化するオブジェクトのランタイム クラスを決定する必要があります。  
  
 `CObject`からクラスを派生するしくみについてはシリアル化を有効にすることで、技術情報 [MFC のファイル](../mfc/files-in-mfc.md) と [シリアル化](../Topic/Serialization%20in%20MFC.md)を参照してください。  
  
## 参照  
 [CObject からのクラスの派生](../mfc/deriving-a-class-from-cobject.md)