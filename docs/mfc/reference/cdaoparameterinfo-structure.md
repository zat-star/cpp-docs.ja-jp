---
title: "CDaoParameterInfo 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoParameterInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoParameterInfo 構造体"
  - "DAO (データ アクセス オブジェクト), Parameters コレクション"
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# CDaoParameterInfo 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDaoParameterInfo` 構造体は、データ アクセス オブジェクト \(DAO\) に対して定義されているパラメーター オブジェクトに関する情報が含まれます。  
  
## 構文  
  
```  
  
      struct CDaoParameterInfo  
{  
   CString m_strName;       // Primary  
   short m_nType;           // Primary  
   ColeVariant m_varValue;  // Secondary  
};  
```  
  
#### パラメーター  
 `m_strName`  
 一意にパラメーター オブジェクトを指定します。  詳細については、DAO ヘルプの「名前」プロパティの参照します。  
  
 `m_nType`  
 パラメーター オブジェクトのデータ型を示す値。  使用できる値の一覧については、[CDaoFieldInfo](../Topic/CDaoFieldInfo%20Structure.md) 構造体の `m_nType` のメンバーを参照してください。  詳細については、DAO ヘルプの「型」プロパティを参照します。  
  
 *m\_varValue*  
 [COleVariant](../../mfc/reference/colevariant-class.md) オブジェクトに格納されているパラメーターの値。  
  
## 解説  
 主キーおよびセカンダリ上への参照は、情報が `CDaoQueryDef`クラスの [GetParameterInfo](../Topic/CDaoQueryDef::GetParameterInfo.md) メンバー関数によってどのように返されるかを示します。  
  
 MFC は DAO クラスのパラメーター オブジェクトをカプセル化します。  MFC `CDaoQueryDef` オブジェクトの基になる DAO のクエリ定義オブジェクトはパラメーター コレクションにパラメーターを格納します。  [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) のパラメーター オブジェクトにアクセスするには、パラメーター コレクションに固有のパラメーター名またはインデックスのクエリ定義オブジェクトの `GetParameterInfo` のメンバー関数に変換し、呼び出します。  `GetParameterInfo` とともにパラメーター コレクションを反復処理するために [CDaoQueryDef::GetParameterCount](../Topic/CDaoQueryDef::GetParameterCount.md) メンバー関数を使用できます。  
  
 [CDaoQueryDef::GetParameterInfo](../Topic/CDaoQueryDef::GetParameterInfo.md) のメンバー関数によって取得される情報は `CDaoParameterInfo` 構造に格納されます。  パラメーター コレクションのパラメーター オブジェクトが格納されているクエリ定義オブジェクトの `GetParameterInfo` を呼び出します。  
  
> [!NOTE]
>  パラメーターの値のみを取得または設定するには、クラス `CDaoRecordset`の [GetParamValue](../Topic/CDaoRecordset::GetParamValue.md) と [SetParamValue](../Topic/CDaoRecordset::SetParamValue.md) メンバー関数を使用します。  
  
 `CDaoParameterInfo` は、デバッグ ビルドの `Dump` のメンバー関数を定義します。  `CDaoParameterInfo` オブジェクトの内容をダンプするために `Dump` を使用できます。  
  
## 必要条件  
 **ヘッダー:** afxdao.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)