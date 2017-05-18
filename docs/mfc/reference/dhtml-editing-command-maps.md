---
title: "DHTML 編集コマンド マップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: c1b49876-039e-4a26-bb24-ea98ccf254a1
caps.latest.revision: 14
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
ms.sourcegitcommit: 17a158366f94d27b7a46917282425d652e6b9042
ms.openlocfilehash: 89aa66d3a1e85183baaba21f001b60e080895f7f
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="dhtml-editing-command-maps"></a>DHTML 編集コマンド マップ
DHTML 編集コマンドをマップする次のマクロを使用できます[関数](../../mfc/reference/chtmleditview-class.md)-クラスを派生します。 使用の例は、次を参照してください。 [HTMLEdit サンプル](../../visual-cpp-samples.md)します。  
  
### <a name="dhtml-editing-command-map-macros"></a>DHTML 編集コマンド マップ マクロ  
  
|||  
|-|-|  
|[DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)|DHTML 編集コマンド マップ クラスで宣言しています。|  
|[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)|DHTML 編集コマンド マップ クラス内での定義を開始します。|  
|[END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)|DHTML 編集コマンド マップの最後をマークします。|  
|[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry)|HTML 編集コマンドをコマンド ID を割り当てます。|  
|[DHTMLEDITING_CMD_ENTRY_FUNC](#dhtmlediting_cmd_entry_func)|HTML 編集コマンドとメッセージ ハンドラーするには、コマンド ID をマップします。|  
|[DHTMLEDITING_CMD_ENTRY_TYPE](#dhtmlediting_cmd_entry_type)|HTML 編集コマンドとユーザー インターフェイス要素には、コマンド ID を割り当てます。|  
|[DHTMLEDITING_CMD_ENTRY_FUNC_TYPE](#dhtmlediting_cmd_entry_func_type)|HTML コマンド、メッセージ ハンドラー、およびユーザー インターフェイス要素を編集するには、コマンド ID をマップします。|  
  
##  <a name="declare_dhtmlediting_cmdmap"></a>DECLARE_DHTMLEDITING_CMDMAP  
 DHTML 編集コマンド マップ クラスで宣言しています。  
  
```  
DECLARE_DHTMLEDITING_CMDMAP(className)   
```  
  
### <a name="parameters"></a>パラメーター  
 `className`  
 クラスの名前。  
  
### <a name="remarks"></a>コメント  
 このマクロの定義で使用するのには、[関数](../../mfc/reference/chtmleditview-class.md)-クラスを派生します。  
  
 使用[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)マップを実装します。  
  
### <a name="example"></a>例  
 参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxhtml.h  
  
##  <a name="begin_dhtmlediting_cmdmap"></a>BEGIN_DHTMLEDITING_CMDMAP  
 DHTML 編集コマンド マップ クラス内での定義を開始します。  
  
```  
BEGIN_DHTMLEDITING_CMDMAP(className)   
```  
  
### <a name="parameters"></a>パラメーター  
 `className`  
 DHTML 編集コマンド マップを含むクラスの名前。 このクラスから直接または間接的を派生する必要があります[関数](../../mfc/reference/chtmleditview-class.md)を含めると、 [DECLARE_DHTMLEDITING_CMDMAP](#declare_dhtmlediting_cmdmap)クラス定義内のマクロです。  
  
### <a name="remarks"></a>コメント  
 DHTML 編集コマンド マップは、ユーザー インターフェイスのコマンドを HTML の編集コマンドにマップするクラスに追加します。  
  
 場所、`BEGIN_DHTMLEDITING_CMDMAP`クラスの実装 (.cpp) ファイルにマクロが続く[DHTMLEDITING_CMD_ENTRY](#dhtmlediting_cmd_entry) 、クラスがマップにコマンドのマクロ (からなど**ID_EDIT_CUT**に**IDM_CUT**)。 使用して、 [END_DHTMLEDITING_CMDMAP](#end_dhtmlediting_cmdmap)イベント マップの最後をマークするマクロ。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxhtml.h  
  
##  <a name="end_dhtmlediting_cmdmap"></a>END_DHTMLEDITING_CMDMAP  
 DHTML 編集コマンド マップの最後をマークします。  
  
```  
END_DHTMLEDITING_CMDMAP()   
```  
  
### <a name="remarks"></a>コメント  
 連携して使用[BEGIN_DHTMLEDITING_CMDMAP](#begin_dhtmlediting_cmdmap)します。  
  
### <a name="example"></a>例  
 参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry"></a>DHTMLEDITING_CMD_ENTRY  
 HTML 編集コマンドをコマンド ID を割り当てます。  
  
```  
DHTMLEDITING_CMD_ENTRY(cmdID,  dhtmlcmdID)   
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdID`  
 コマンド ID (たとえば**ID_EDIT_COPY**)。  
  
 `dhtmlcmdID`  
 編集コマンドを HTML`cmdID`マップ (よう**IDM_COPY**)。  
  
### <a name="example"></a>例  
 参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_func"></a>DHTMLEDITING_CMD_ENTRY_FUNC  
 HTML 編集コマンドとメッセージ ハンドラーするには、コマンド ID をマップします。  
  
```  
DHTMLEDITING_CMD_ENTRY_FUNC(cmdID, dhtmlcmdID,  member_func_name)   
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdID`  
 コマンド ID (たとえば**ID_EDIT_COPY**)。  
  
 `dhtmlcmdID`  
 編集コマンドを HTML`cmdID`マップ (よう**IDM_COPY**)。  
  
 `member_func_name`  
 コマンドがマップされているメッセージ ハンドラー関数の名前。  
  
### <a name="example"></a>例  
 参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_type"></a>DHTMLEDITING_CMD_ENTRY_TYPE  
 HTML 編集コマンドとユーザー インターフェイス要素には、コマンド ID を割り当てます。  
  
```  
DHTMLEDITING_CMD_ENTRY_TYPE(cmdID  ,   dhtmlcmdID  ,    elemType)  
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdID`  
 コマンド ID (たとえば**ID_EDIT_COPY**)。  
  
 `dhtmlcmdID`  
 編集コマンドを HTML`cmdID`マップ (よう**IDM_COPY**)。  
  
 `elemType`  
 ユーザー インターフェイス要素の型。いずれかの**AFX_UI_ELEMTYPE_NORMAL**、 **AFX_UI_ELEMTYPE_CHECKBOX**、または**AFX_UI_ELEMTYPE_RADIO**します。  
  
### <a name="example"></a>例  
 参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)します。  
  
### <a name="requirements"></a>要件  
  **ヘッダー** afxhtml.h  
  
##  <a name="dhtmlediting_cmd_entry_func_type"></a>DHTMLEDITING_CMD_ENTRY_FUNC_TYPE  
 HTML コマンド、メッセージ ハンドラー、およびユーザー インターフェイス要素を編集するには、コマンド ID をマップします。  
  
```  
DHTMLEDITING_CMD_ENTRY_FUNC_TYPE(cmdID, dhtmlcmdID, member_func_name,  elemType)   
```  
  
### <a name="parameters"></a>パラメーター  
 `cmdID`  
 コマンド ID (たとえば**ID_EDIT_COPY**)。  
  
 `dhtmlcmdID`  
 編集コマンドを HTML`cmdID`マップ (よう**IDM_COPY**)。  
  
 `member_func_name`  
 コマンドがマップされているメッセージ ハンドラー関数の名前。  
  
 `elemType`  
 ユーザー インターフェイス要素の型。いずれかの**AFX_UI_ELEMTYPE_NORMAL**、 **AFX_UI_ELEMTYPE_CHECKBOX**、または**AFX_UI_ELEMTYPE_RADIO**します。  
  
### <a name="example"></a>例  
 参照してください[HTMLEdit サンプル](../../visual-cpp-samples.md)します。  

### <a name="requirements"></a>要件  
  **ヘッダー** afxhtml.h  
    
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

