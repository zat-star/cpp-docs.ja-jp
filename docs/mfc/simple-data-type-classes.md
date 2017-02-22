---
title: "単純データ型クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "データ クラス [C++]"
  - "スカラー クラス [C++]"
  - "単純なデータ型クラス"
ms.assetid: 0d591d68-0a33-49e9-8a6d-90c90de5c16a
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# 単純データ型クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のクラスは、C\+\+ の構文を便利に使用できるように、描画座標、文字列、および時間と日付の情報をカプセル化します。  これらのオブジェクトはクラス ライブラリの Windows クラスのメンバー関数のパラメーターとして広く使われます。  `CPoint`、`CSize`、および `CRect` は、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)] ではそれぞれ、**POINT**、**SIZE**、および `RECT` の各構造体に対応しているので、これらの C 言語の構造体を使用できる場所ならどこでもこれら C\+\+ クラスのオブジェクトを使用できます。  このクラスは、メンバー関数を介して役に立つインターフェイスを提供します。  `CStringT` は、非常に柔軟で動的な文字列を提供します。  `CTime`、`COleDateTime`、`CTimeSpan`、および **COleTimeSpan** は、時間と日付の値を表現します。  これらのクラスの詳細については、「[日付と時刻](../atl-mfc-shared/date-and-time.md)」を参照してください。  
  
 "**COle**" で始まるクラスは OLE で提供されるデータ型をカプセル化します。  これらのデータ型は別の OLE 機能が使われているかどうかにかかわらず Windows プログラムで使用できます。  
  
 [CStringT クラス](../atl-mfc-shared/reference/cstringt-class.md)  
 文字列を保持します。  
  
 [CTime](../Topic/CTime%20Class.md)  
 絶対的な時間と日付の値を保持します。  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 OLE オートメーション型 **DATE** のラッパー。  日付と時間の値を表現します。  
  
 [CTimeSpan](../atl-mfc-shared/reference/ctimespan-class.md)  
 相対的な時間と日付の値を保持します。  
  
 [COleDateTimeSpan](../Topic/COleDateTimeSpan%20Class.md)  
 2 つの `COleDateTime` 値の差などの相対的な `COleDateTime` 値を保持します。  
  
 [CPoint](../Topic/CPoint%20Class.md)  
 座標 \(x, y\) のペアを保持します。  
  
 [CSize](../atl-mfc-shared/reference/csize-class.md)  
 距離、相対位置、または値のペアを保持します。  
  
 [CRect](../atl-mfc-shared/reference/crect-class.md)  
 四角形領域の座標を保持します。  
  
 [CImageList](../Topic/CImageList%20Class.md)  
 Windows イメージ リストの機能が用意されています。  イメージ リストはリスト コントロールやツリー コントロールで使われます。  また、同じサイズのビットマップの組の格納や保存にも使用できます。  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 OLE オートメーション型 **VARIANT** のラッパー。  **VARIANT** のデータは、いろいろな形式で格納されます。  
  
 [COleCurrency](../Topic/COleCurrency%20Class.md)  
 整数部 15 桁、小数部 4 桁の固定小数点の数値型である OLE オートメーション型 **CURRENCY** のラッパー。  
  
> [!NOTE]
>  Visual C\+\+ .NET 以降では、`CRect`、`CSize`、および `CPoint` は、ATL アプリケーション、MFC アプリケーションのどちらにおいても使用できるように修正されています。  さらに、MFC から独立した `CString` のようなクラスを提供するために、`CStringT` が追加されています。  共有ユーティリティ クラスの詳細については、「[共有クラス](../atl-mfc-shared/atl-mfc-shared-classes.md)」を参照してください。  
  
## 参照  
 [クラスの概要](../mfc/class-library-overview.md)