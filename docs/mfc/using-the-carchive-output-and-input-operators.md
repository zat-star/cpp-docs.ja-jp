---
title: "CArchive 演算子 &lt;&lt; および &gt;&gt; の使用法 | Microsoft Docs"
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
  - "CArchive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive クラス, 演算子"
  - "CArchive クラス, 格納と読み込み (オブジェクトの)"
  - "オブジェクト [C++], 読み込み (直前の格納値から)"
ms.assetid: 56aef326-02dc-4992-8282-f0a4b78a064e
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CArchive 演算子 &lt;&lt; および &gt;&gt; の使用法
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CArchive` は 単純データ型を \<\< 作成して \>\> 読み取りを演算子は、ファイルに対する `CObject`s を提供します。  
  
#### オブジェクトをアーカイブによってファイルに格納します。  
  
1.  次の例では、アーカイブによってファイルのオブジェクトを保存する方法を示します。:  
  
     [!code-cpp[NVC_MFCSerialization#7](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_1.cpp)]  
  
#### 前にファイルに格納されている値からオブジェクトを読み込むには  
  
1.  次の例は、前にファイルに格納されている値からオブジェクトを読み込む方法の設定:  
  
     [!code-cpp[NVC_MFCSerialization#8](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_2.cpp)]  
  
 通常、`CObject`の `Serialize` 関数 \(ユーザーが **DECLARE\_SERIALIZE** マクロを使って宣言されている必要のある派生クラスでアーカイブしてファイルに対するロード データ保存します。  `CArchive` オブジェクトへの参照が `Serialize` 関数に渡されます。  `Serialize` 関数がファイルまたはデータ ストアからファイルへのロード データに呼び出されるかどうかを確認するに `CArchive` オブジェクトの `IsLoading` 関数を呼び出します。  
  
 シリアル `CObject`の `Serialize` 関数\-派生クラスに、次のフォームがあります:  
  
 [!code-cpp[NVC_MFCSerialization#9](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_3.cpp)]  
  
 上記のコード テンプレートは厳密に 1 AppWizard がドキュメント \(**CDocument\)**の `Serialize` 関数に対してから派生したクラスを作成するのと同じです。  このコード テンプレートは次の例のように保存コードと読み込みコードが平行常に必要なので、確認しやすいコードを作成するための T:  
  
 [!code-cpp[NVC_MFCSerialization#10](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_4.cpp)]  
  
 ライブラリは 2 番目のオペランドが 1 番目のオペランドと `CArchive` の **\<\<** と **\>\>** の演算子と、次のデータ型とクラス型定義します:  
  
||||  
|-|-|-|  
|`CObject*`|**サイズおよび CSize**|**float**|  
|**WORD**|`CString`|**POINT** と `CPoint`|  
|`DWORD`|**BYTE**|`RECT` および `CRect`|  
|**Double**|**LONG**|`CTime` および `CTimeSpan`|  
|`Int`|**COleCurrency**|`COleVariant`|  
|`COleDateTime`|`COleDateTimeSpan`||  
  
> [!NOTE]
>  アーカイブして `CObject`s を格納および読み込むと、余分な事項を考慮する必要があります。  詳細については、「[CObjects をアーカイブに格納し、読み込みます](../Topic/Storing%20and%20Loading%20CObjects%20via%20an%20Archive.md)」を参照してください。  
  
 **CArchive \<\<** と **\>\>** の演算子は 1 番目のオペランドである `CArchive` オブジェクトへの参照を返します。  これは、後で説明するように、チェーンを演算子を使用すると、T:  
  
 [!code-cpp[NVC_MFCSerialization#11](../mfc/codesnippet/CPP/using-the-carchive-output-and-input-operators_5.cpp)]  
  
## 参照  
 [シリアル化 : オブジェクトのシリアル化](../Topic/Serialization:%20Serializing%20an%20Object.md)