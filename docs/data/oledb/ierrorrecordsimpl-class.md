---
title: "IErrorRecordsImpl クラス | Microsoft Docs"
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
  - "ATL::IErrorRecordsImpl"
  - "ATL.IErrorRecordsImpl"
  - "IErrorRecordsImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IErrorRecordsImpl クラス"
ms.assetid: dea8e938-c5d8-45ab-86de-eb8fbf534ffb
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IErrorRecordsImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

レコードを追加し、型 **CAtlArray\<**`RecordClass`**\>**のデータ メンバー \([m\_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)\) からレコードを取得する OLE DB の [IErrorRecords](https://msdn.microsoft.com/en-us/library/ms718112.aspx) インターフェイスを実装します。  
  
## 構文  
  
```  
template <  
   class T,   
   class RecordClass = ATLERRORINFO  
>  
class IErrorRecordsImpl : public IErrorRecords  
```  
  
#### パラメーター  
 `T`  
 `IErrorRecordsImpl`から派生したクラスです。  
  
 `RecordClass`  
 OLE DB の Error オブジェクトを表すクラスです。  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[GetErrorDescriptionString](../../data/oledb/ierrorrecordsimpl-geterrordescriptionstring.md)|エラー レコードからエラーを説明する文字列を取得します。|  
|[GetErrorGUID](../../data/oledb/ierrorrecordsimpl-geterrorguid.md)|エラー レコードからエラー GUID を取得します。|  
|[GetErrorHelpContext](../../data/oledb/ierrorrecordsimpl-geterrorhelpcontext.md)|エラー レコードからヘルプ コンテキスト ID を取得します。|  
|[GetErrorHelpFile](../../data/oledb/ierrorrecordsimpl-geterrorhelpfile.md)|エラー レコードからヘルプ ファイルの完全パス名を取得します。|  
|[GetErrorSource](../../data/oledb/ierrorrecordsimpl-geterrorsource.md)|エラー レコードからエラー ソース・コードを取得します。|  
  
### インターフェイス メソッド  
  
|||  
|-|-|  
|[AddErrorRecord](../Topic/IErrorRecordsImpl::AddErrorRecord.md)|OLE DB の Error オブジェクトにレコードを追加します。|  
|[GetBasicErrorInfo](../../data/oledb/cdberrorinfo-getbasicerrorinfo.md)|リターン コードとプロバイダー固有のエラー番号などの基本情報を返します。|  
|[GetCustomErrorObject](../../data/oledb/cdberrorinfo-getcustomerrorobject.md)|カスタム エラー オブジェクトのインターフェイスへのポインターを返します。|  
|[GetErrorInfo](../../data/oledb/cdberrorinfo-geterrorinfo.md)|指定した数の [IErrorInfo](https://msdn.microsoft.com/en-us/library/ms718112.aspx) インターフェイス ポインターを返します。|  
|[GetErrorParameters](../../data/oledb/cdberrorinfo-geterrorparameters.md)|エラー パラメーターを返します。|  
|[GetRecordCount](../Topic/CDaoRecordset::GetRecordCount.md)|OLE DB のレコード オブジェクト内のレコード数を返します。|  
  
### データ メンバー  
  
|||  
|-|-|  
|[m\_rgErrors](../../data/oledb/ierrorrecordsimpl-m-rgerrors.md)|エラー レコードの配列。|  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)