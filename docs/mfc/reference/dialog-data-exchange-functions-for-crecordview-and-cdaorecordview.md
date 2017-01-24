---
title: "CRecordView と CDaoRecordView のダイアログ データ エクスチェンジ (DDX) 関数 | Microsoft Docs"
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
  - "vc.mfc.macros.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO [C++], ダイアログ データ エクスチェンジ (DDX) のサポート"
  - "データベース [C++], ダイアログ データ エクスチェンジ (DDX) のサポート"
  - "DDX (ダイアログ データ エクスチェンジ) [C++], データベースのサポート"
  - "DDX (ダイアログ データ エクスチェンジ) [C++], 関数"
  - "DDX_Field 関数"
  - "ODBC [C++], ダイアログ データ エクスチェンジ (DDX) のサポート"
ms.assetid: 0d8cde38-3a2c-4100-9589-ac80a7b1ce91
caps.latest.revision: 13
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRecordView と CDaoRecordView のダイアログ データ エクスチェンジ (DDX) 関数
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このトピックでは [CRecordset](../Topic/CRecordset%20Class.md) と [CRecordView](../../mfc/reference/crecordview-class.md) のフォーム間でデータをやり取りしてまたは [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) と [CDaoRecordView クラス](../../mfc/reference/cdaorecordview-class.md) のフォーム DDX\_Field 使用される関数の一覧を示します。  
  
> [!NOTE]
>  DDX\_Field 関数は DDX 関数のようにフォームのコントロールとのデータ交換です。  ただし、DDX とは異なり、レコード ビューのフィールド自体ではなく、ビューの関連レコードセット オブジェクトのフィールドとデータを交換します。  詳細については、クラスに `CRecordView` と `CDaoRecordView`を参照します。  
  
### DDX\_Field 関数  
  
|||  
|-|-|  
|[DDX\_FieldCBIndex](../Topic/DDX_FieldCBIndex.md)|レコードセット フィールド データ メンバーと [CRecordView](../../mfc/reference/crecordview-class.md) のコンボ ボックスの現在の選択項目のインデックスまたは [CDaoRecordView クラス](../../mfc/reference/cdaorecordview-class.md)間の整数データ。|  
|[DDX\_FieldCBString](../Topic/DDX_FieldCBString.md)|レコードセット フィールド データ メンバーと `CRecordView` のコンボ ボックスのエディット コントロールまたは `CDaoRecordView`間の `CString` データ。  レコードセットのコントロールへのデータの移動が、この関数は、指定された文字列の文字で始まるコンボ ボックスの項目を選択したときに表示されます。|  
|[DDX\_FieldCBStringExact](../Topic/DDX_FieldCBStringExact.md)|レコードセット フィールド データ メンバーと `CRecordView` のコンボ ボックスのエディット コントロールまたは `CDaoRecordView`間の `CString` データ。  レコードセットのコントロールへのデータの移動が、この関数は、指定した文字列に一致するコンボ ボックスの項目を選択したときに表示されます。|  
|[DDX\_FieldCheck](../Topic/DDX_FieldCheck.md)|レコードセット フィールド データ メンバーと `CRecordView` チェック ボックスまたは `CDaoRecordView`間の Boolean データ。|  
|[DDX\_FieldLBIndex](../Topic/DDX_FieldLBIndex.md)|レコードセット フィールド データ メンバーと `CRecordView` ボックスの一覧の現在の選択項目のインデックスまたは `CDaoRecordView`間の整数データ。|  
|[DDX\_FieldLBString](../Topic/DDX_FieldLBString.md)|リスト ボックス コントロールとレコードセットのフィールド データ メンバー間でデータを転送 [CString](../../atl-mfc-shared/reference/cstringt-class.md) を管理します。  レコードセットのコントロールへのデータの移動が、この関数は、指定された文字列の文字で始まるリスト ボックスの項目を選択したときに表示されます。|  
|[DDX\_FieldLBStringExact](../Topic/DDX_FieldLBStringExact.md)|リスト ボックス コントロールとレコードセットのフィールド データ メンバー間でデータを転送 `CString` を管理します。  レコードセットのコントロールへのデータの移動が、この関数は、指定した文字列に一致する最初の項目を選択したときに表示されます。|  
|[DDX\_FieldRadio](../Topic/DDX_FieldRadio.md)|レコードセット フィールド データ メンバーと `CRecordView` のオプション ボタン グループまたは `CDaoRecordView`間の整数データ。|  
|[DDX\_FieldScroll](../Topic/DDX_FieldScroll.md)|設定は、`CRecordView` または `CDaoRecordView`のスクロール バー コントロールのスクロール位置を取得します。  [DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md) 関数からの呼び出し。|  
|[DDX\_FieldText](../Topic/DDX_FieldText.md)|オーバーロードされたバージョンをレコードセット フィールド データ メンバーと `CRecordView` のエディット ボックスまたは `CDaoRecordView`の間で `int`、**UINT**、**long**、`DWORD`、[CString](../../atl-mfc-shared/reference/cstringt-class.md)、**float**、**double**、**short**、[COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)と [COleCurrency](../Topic/COleCurrency%20Class.md) データを転送するために使用できます。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)