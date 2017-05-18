---
title: "CDaoWorkspaceInfo 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoWorkspaceInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoWorkspaceInfo structure
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 44c1ce365a1eecdb2a500998c082c6a9245dffb2
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoworkspaceinfo-structure"></a>CDaoWorkspaceInfo 構造体
`CDaoWorkspaceInfo`構造体には、データ アクセス オブジェクト (DAO) のデータベース アクセスに対して定義されているワークスペースについての情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
struct CDaoWorkspaceInfo  
{  
    CString m_strName;           // Primary  
    CString m_strUserName;       // Secondary  
    BOOL m_bIsolateODBCTrans;    // All  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 `m_strName`  
 Workspace オブジェクトの一意名します。 このプロパティの値を直接取得するには、クエリ定義オブジェクトを呼び出す[GetName](../../mfc/reference/cdaoquerydef-class.md#getname)メンバー関数。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
 *m_strUserName*  
 Workspace オブジェクトの所有者を表す値。 関連情報については、DAO ヘルプの「ユーザー名プロパティ」を参照してください。  
  
 *m_bIsolateODBCTrans*  
 同じ ODBC データベースが関係する複数のトランザクションが分離されたかどうかを示す値です。 詳細については、次を参照してください。 [CDaoWorkspace::SetIsolateODBCTrans](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans)します。 関連情報については、DAO ヘルプの「IsolateODBCTrans プロパティ」を参照してください。  
  
## <a name="remarks"></a>コメント  
 ワークスペースは、クラスのオブジェクトを[CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)します。 プライマリ、セカンダリ データベースを上記のすべての参照がによって情報が返される方法を示す、 [GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo)クラスのメンバー関数`CDaoWorkspace`します。  
  
 によって取得される情報、 [CDaoWorkspace::GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo)メンバー関数は、`CDaoWorkspaceInfo`構造体。 `CDaoWorkspaceInfo`定義して、`Dump`デバッグでのメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoWorkspaceInfo`オブジェクトです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace クラス](../../mfc/reference/cdaoworkspace-class.md)

