---
title: "ランタイム クラス情報へのアクセス方法 | Microsoft Docs"
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
  - "クラス [C++], ランタイム クラス情報"
  - "CObject クラス, アクセス (ランタイム クラス情報に)"
  - "CObject クラス, および RTTI"
  - "CObject クラス, 使用 (IsKindOf メソッドを)"
  - "CObject クラス, 使用 (RUNTIME_CLASS マクロを)"
  - "IsKindOf メソッド"
  - "RTTI コンパイラ オプション"
  - "実行時に"
  - "実行時に, クラス情報"
  - "ランタイム クラス"
  - "ランタイム クラス, アクセス (情報に)"
  - "RUNTIME_CLASS マクロ"
  - "RUNTIME_CLASS マクロ, 使用"
ms.assetid: 3445a9af-0bd6-4496-95c3-aa59b964570b
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ランタイム クラス情報へのアクセス方法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは実行時にオブジェクトのクラスについての情報にアクセスする方法について説明します。  
  
> [!NOTE]
>  MFC は、Visual C\+\+ 4.0 で行った [ランタイム型情報](../Topic/Run-Time%20Type%20Information.md) \(RTTI\) サポートを使用しません。  
  
 [CObject](../Topic/CObject%20Class.md) からクラスを派生し、技術情報 [CObject からクラスを派生すること](../mfc/deriving-a-class-from-cobject.md)で **DECLARE**bind \(**DYNAMIC** と `IMPLEMENT_DYNAMIC`、`DECLARE_DYNCREATE` と `IMPLEMENT_DYNCREATE`、または説明する `DECLARE_SERIAL` と `IMPLEMENT_SERIAL` マクロを使用している場合は、`CObject` クラスに実行時にオブジェクトの正確なクラスを決定する機能があります。  
  
 この機能は、関数の引数の特別な型チェックが必要なときや、オブジェクトのクラスによって、コードを記述する場合に便利です。  ただし、この手法は通常、仮想関数の機能を複製するため、推奨されません。  
  
 `CObject` のメンバー関数 `IsKindOf` が使用できる特定のオブジェクトが特定のクラスに属するかどうかを判断するためにクラスから派生されれば。  `IsKindOf` への引数は、クラス名の `RUNTIME_CLASS` マクロを使用して取得できます。`CRuntimeClass` オブジェクトです。  
  
### RUNTIME\_CLASS マクロを使用します。  
  
1.  クラス `CObject`には次に示すように、クラス名の `RUNTIME_CLASS` を使用する:  
  
     [!code-cpp[NVC_MFCCObjectSample#4](../mfc/codesnippet/CPP/accessing-run-time-class-information_1.cpp)]  
  
 ほとんどのランタイム クラスのオブジェクトに直接アクセスする必要はありません。  一般的な用途は、次の手順に示すように `IsKindOf` 関数へのランタイム クラス オブジェクトを渡すことです。  特定のクラスに属する場合 `IsKindOf` 関数参照するテストするオブジェクト。  
  
#### IsKindOf 関数を使用します。  
  
1.  クラスのランタイム クラスがサポートされていることを確認します。  つまり、クラスは `CObject` から直接的または間接的に派生されたいる必要があり、技術情報 [CObject からクラスを派生すること](../mfc/deriving-a-class-from-cobject.md)で **DECLARE**bind \(**DYNAMIC** と `IMPLEMENT_DYNAMIC`、`DECLARE_DYNCREATE` と `IMPLEMENT_DYNCREATE`、または説明する `DECLARE_SERIAL` と `IMPLEMENT_SERIAL` のマクロを使用します。  
  
2.  次に示すように `CRuntimeClass` の引数を生成するために `RUNTIME_CLASS` マクロを使用してクラスのオブジェクトの `IsKindOf` のメンバー関数を呼び出します。:  
  
     [!code-cpp[NVC_MFCCObjectSample#2](../mfc/codesnippet/CPP/accessing-run-time-class-information_2.h)]  
  
     [!code-cpp[NVC_MFCCObjectSample#5](../mfc/codesnippet/CPP/accessing-run-time-class-information_3.cpp)]  
  
    > [!NOTE]
    >  IsKindOf はオブジェクトが指定されたクラス、またはそのクラスから派生したクラスのメンバーである場合 **TRUE** を返します。  `IsKindOf` は 派生の Microsoft Foundation Class に多重継承を必要に応じて使用できますが、多重継承または仮想基本クラスをサポートしません。  
  
 ランタイム クラス情報を 1 回使用はオブジェクトの動的生成にあります。  このプロセスは、記事 [動的オブジェクトの作成](../Topic/Dynamic%20Object%20Creation.md)で説明します。  
  
 シリアル化、およびランタイム クラス情報の詳細については、"情報 [MFC のファイル](../mfc/files-in-mfc.md) と [シリアル化](../Topic/Serialization%20in%20MFC.md)を参照してください。  
  
## 参照  
 [CObject の使い方](../mfc/using-cobject.md)