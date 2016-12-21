---
title: "レコードセット: ブックマークと絶対位置 (ODBC) | Microsoft Docs"
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
  - "SetAbsolutePosition"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "絶対位置, ODBC レコードセット"
  - "ブックマーク"
  - "ブックマーク, CDBVariant"
  - "ブックマーク, ODBC レコードセット"
  - "CDBVariant クラス, ブックマーク"
  - "カーソル [ODBC], 絶対位置 (レコードセットの)"
  - "GetBookmark メソッド"
  - "ODBC レコードセット, 絶対位置"
  - "ODBC レコードセット, ブックマーク"
  - "配置 (レコードを)"
  - "レコードの配置"
  - "レコードセット, 絶対位置"
  - "レコードセット, ブックマーク"
  - "SetAbsolutePosition メソッド"
  - "SetAbsolutePosition メソッド, ブックマーク"
  - "SetBookmark メソッド"
ms.assetid: 189788d6-33c1-41c5-9265-97db2a5d43cc
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# レコードセット: ブックマークと絶対位置 (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックの内容は、MFC ODBC クラスに該当します。  
  
 レコードセット内を移動していると、しばしば特定のレコードに戻る必要が生じます。  特定のレコードに戻るには、レコードのブックマークと絶対位置という 2 つの手段があります。  
  
 このトピックでは、次の内容について説明します。  
  
-   [ブックマークの使い方](#_core_bookmarks_in_mfc_odbc)  
  
-   [絶対位置を使って現在のレコードを設定する方法](#_core_absolute_positions_in_mfc_odbc)  
  
##  <a name="_core_bookmarks_in_mfc_odbc"></a> MFC ODBC のブックマーク  
 ブックマークは、レコードを一意に識別します。  レコードセット内を移動する場合、レコードセットからレコードが削除されることがあるため、必ずしもレコードの絶対位置に頼ることはできません。  レコードの位置を確実に決定できるようにするには、ブックマークを使用します。  `CRecordset` クラスには、以下のようなメンバー関数が用意されています。  
  
-   現在のレコードのブックマークを取得し、それを変数内に保存するための [GetBookmark](../Topic/CRecordset::GetBookmark.md) 関数  
  
-   変数内に保存されたブックマークを指定し、特定のレコードにすばやく移動するための [SetBookmark](../Topic/CRecordset::SetBookmark.md) 関数  
  
 次の例は、この 2 つのメンバー関数を使用して、現在のレコードをマークし、そのレコードに後で戻るための方法を示しています。  
  
```  
// rs is a CRecordset or  
// CRecordset-derived object  
  
CDBVariant varRecordToReturnTo;  
rs.GetBookmark( varRecordToReturnTo );  
  
// More code in which you  
// move to other records  
  
rs.SetBookmark( varRecordToReturnTo );  
```  
  
 [CDBVariant クラス](../Topic/CDBVariant%20Class.md) オブジェクトから、基になるデータ型を取り出す必要はありません。  `GetBookmark` でブックマークの値を指定し、そのブックマークに `SetBookmark` で戻ります。  
  
> [!NOTE]
>  ODBC ドライバーとレコードセットの種類によっては、ブックマークがサポートされない場合があります。  ブックマークがサポートされているかどうかは、[CRecordset::CanBookmark](../Topic/CRecordset::CanBookmark.md) を呼び出して簡単に確認できます。  ブックマークがサポートされている場合でも、[CRecordset::Open](../Topic/CRecordset::Open.md) メンバー関数の **CRecordset::useBookmarks** オプションを指定して、ブックマークを明示的に実装する必要があります。  また、レコードセットに対する操作の種類によっては、操作を実行した後に、ブックマークが無効になっていないかどうかを確認する必要があります。  たとえば、**Requery** でレコードセットのクエリを再実行すると、ブックマークが有効ではなくなる場合があります。  `SetBookmark` を安全に呼び出すことができるかどうかをチェックするには、[CDatabase::GetBookmarkPersistence](../Topic/CDatabase::GetBookmarkPersistence.md) を呼び出します。  
  
##  <a name="_core_absolute_positions_in_mfc_odbc"></a> MFC ODBC の絶対位置  
 `CRecordset` では、ブックマークのほかに、位置を使って現在のレコードを設定することもできます。  この方法は、絶対ポジショニングと呼ばれます。  
  
> [!NOTE]
>  絶対ポジショニングは、前方スクロール専用レコードセットには使用できません。  前方スクロール専用レコードセットの詳細については、「[レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)」を参照してください。  
  
 絶対位置を使用して現在のレコードを移動するには、[CRecordset::SetAbsolutePosition](../Topic/CRecordset::SetAbsolutePosition.md) を呼び出します。  `SetAbsolutePosition` に値を渡すと、その位置に対応するレコードが現在のレコードになります。  
  
> [!NOTE]
>  レコードの絶対位置は、信頼できない場合があります。  レコードセットからレコードが削除されると、それ以降のレコードの位置が変更されるためです。  現在のレコードを移動するには、ブックマークを使用することをお勧めします。  詳細については、「[MFC での MAPI サポート](#_core_bookmarks_in_mfc_odbc)」を参照してください。  
  
 レコードセットの移動の詳細については、「\<[レコードセット: スクロール \(ODBC\)](../Topic/Recordset:%20Scrolling%20\(ODBC\).md)」を参照してください。  
  
## 参照  
 [レコードセット \(ODBC\)](../../data/odbc/recordset-odbc.md)