---
title: "CDBErrorInfo::GetAllErrorInfo | Microsoft Docs"
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
  - "ATL.CDBErrorInfo.GetAllErrorInfo"
  - "CDBErrorInfo::GetAllErrorInfo"
  - "ATL::CDBErrorInfo::GetAllErrorInfo"
  - "GetAllErrorInfo"
  - "CDBErrorInfo.GetAllErrorInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetAllErrorInfo メソッド"
ms.assetid: 630049fa-d296-497a-bbf6-f5d3d71d271d
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBErrorInfo::GetAllErrorInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

エラー レコードに含まれるエラー情報のすべての型を返します。  
  
## 構文  
  
```  
  
      HRESULT GetAllErrorInfo(  
   ULONG ulRecordNum,  
   LCID lcid,  
   BSTR* pbstrDescription,  
   BSTR* pbstrSource = NULL,  
   GUID* pguid = NULL,  
   DWORD* pdwHelpContext = NULL,  
   BSTR* pbstrHelpFile = NULL  
) const throw( );  
```  
  
#### パラメーター  
 *ulRecordNum*  
 \[\]エラー情報を返すレコードのインデックス番号が 0 から始まるの数。  
  
 `lcid`  
 \[\]返されるエラー情報のロケール ID。  
  
 `pbstrDescription`  
 \[\]ロケールがサポートされていない場合は、エラーまたは null のテキスト説明へのポインター。  「解説」を参照してください。  
  
 `pbstrSource`  
 \[\]文字列へのポインター。エラーが発生したコンポーネントの名前。  
  
 `pguid`  
 \[\]エラーを定義するインターフェイスの GUID へのポインター。  
  
 *pdwHelpContext*  
 \[\]エラーのヘルプ コンテキスト ID へのポインター。  
  
 *pbstrHelpFile*  
 \[\]文字列へのポインター。エラーを説明するヘルプ ファイルのパス。  
  
## 戻り値  
 正常に終了した場合は `S_OK`。  他の戻り値の *OLE DB Programmer's Reference* の [IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx) を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 解説  
 `pbstrDescription` の出力値を null に値を設定する IErrorInfo::GetDescription を呼び出してロケールがサポートされていない場合、または次の両方の条件が true の場合、内部的により、:  
  
1.  `lcid` の値は米国の英語ではありません。  
  
2.  `lcid` の値は GetUserDefaultLCID によって返される値と同等です。  
  
## 参照  
 [CDBErrorInfo クラス](../../data/oledb/cdberrorinfo-class.md)