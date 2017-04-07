---
title: "メンバー クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDispatchException
- AFXDISP/COleDispatchException
- AFXDISP/COleDispatchException::m_dwHelpContext
- AFXDISP/COleDispatchException::m_strDescription
- AFXDISP/COleDispatchException::m_strHelpFile
- AFXDISP/COleDispatchException::m_strSource
- AFXDISP/COleDispatchException::m_wCode
dev_langs:
- C++
helpviewer_keywords:
- COleDispatchException class
- Automation, exceptions
- exceptions, OLE
- OLE exceptions, to IDispatch interface
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
caps.latest.revision: 22
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 0071e57b6c8f6bec73712186e8ff8baa9bfcc165
ms.lasthandoff: 02/24/2017

---
# <a name="coledispatchexception-class"></a>メンバー クラス
OLE オートメーションの主要部分である OLE `IDispatch` インターフェイス固有の例外を処理します。  
  
## <a name="syntax"></a>構文  
  
```  
class COleDispatchException : public CException  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[COleDispatchException::m_dwHelpContext](#m_dwhelpcontext)|エラーのヘルプ コンテキスト。|  
|[COleDispatchException::m_strDescription](#m_strdescription)|言葉によるエラーの説明。|  
|[COleDispatchException::m_strHelpFile](#m_strhelpfile)|ヘルプで使用するファイル`m_dwHelpContext`します。|  
|[COleDispatchException::m_strSource](#m_strsource)|例外を生成したアプリケーションです。|  
|[COleDispatchException::m_wCode](#m_wcode)|`IDispatch`-特定のエラー コード。|  
  
## <a name="remarks"></a>コメント  
 派生したその他の例外クラスと同様に、`CException`基本クラス、`COleDispatchException`と併用して、**スロー**、 `THROW_LAST`、**しようと**、**キャッチ**、 `AND_CATCH`、および`END_CATCH`マクロです。  
  
 一般を呼び出す必要があります[AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception)を作成し、スロー、`COleDispatchException`オブジェクトです。  
  
 例外の詳細については、記事を参照してください。[例外処理 (MFC)](../../mfc/exception-handling-in-mfc.md)と[例外: OLE の例外](../../mfc/exceptions-ole-exceptions.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleDispatchException`  
  
## <a name="requirements"></a>要件  
 **ヘッダー :** afxdisp.h  
  
##  <a name="m_dwhelpcontext"></a>COleDispatchException::m_dwHelpContext  
 アプリケーションのヘルプのヘルプ コンテキストを識別する (。HLP) ファイルです。  
  
```  
DWORD m_dwHelpContext;  
```  
  
### <a name="remarks"></a>コメント  
 このメンバーは、関数に設定されます。 [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception)例外がスローされます。  
  
### <a name="example"></a>例  
  例を参照してください[COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)します。  
  
##  <a name="m_strdescription"></a>COleDispatchException::m_strDescription  
 "ディスクがいっぱいです"などの口頭でのエラーの説明が含まれています  
  
```  
CString m_strDescription;  
```  
  
### <a name="remarks"></a>コメント  
 このメンバーは、関数に設定されます。 [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception)例外がスローされます。  
  
### <a name="example"></a>例  
  例を参照してください[COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)します。  
  
##  <a name="m_strhelpfile"></a>COleDispatchException::m_strHelpFile  
 フレームワークは、アプリケーションのヘルプ ファイルの名前では、この文字列に格納します。  
  
```  
CString m_strHelpFile;  
```  
  
##  <a name="m_strsource"></a>COleDispatchException::m_strSource  
 フレームワークは、例外を生成したアプリケーションの名前では、この文字列に格納します。  
  
```  
CString m_strSource;  
```  
  
### <a name="example"></a>例  
  例を参照してください[COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch)します。  
  
##  <a name="m_wcode"></a>COleDispatchException::m_wCode  
 アプリケーションに固有のエラー コードが含まれています。  
  
```  
WORD m_wCode;  
```  
  
### <a name="remarks"></a>コメント  
 このメンバーは、関数に設定されます。 [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception)例外がスローされます。  
  
## <a name="see-also"></a>関連項目  
 [MFC サンプル CALCDRIV](../../visual-cpp-samples.md)   
 [CException クラス](../../mfc/reference/cexception-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [ディスパッチ クラス](../../mfc/reference/coledispatchdriver-class.md)   
 [関数のクラス](../../mfc/reference/coleexception-class.md)

