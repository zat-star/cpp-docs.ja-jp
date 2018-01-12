---
title: "Cdberrorinfo::getallerrorinfo |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL.CDBErrorInfo.GetAllErrorInfo
- CDBErrorInfo::GetAllErrorInfo
- ATL::CDBErrorInfo::GetAllErrorInfo
- GetAllErrorInfo
- CDBErrorInfo.GetAllErrorInfo
dev_langs: C++
helpviewer_keywords: GetAllErrorInfo method
ms.assetid: 630049fa-d296-497a-bbf6-f5d3d71d271d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 46e233800f814b39e4e14f0b357c381a3e71311e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="cdberrorinfogetallerrorinfo"></a>CDBErrorInfo::GetAllErrorInfo
すべての種類のエラー レコードに含まれているエラー情報を返します。  
  
## <a name="syntax"></a>構文  
  
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
  
#### <a name="parameters"></a>パラメーター  
 *ulRecordNum*  
 [in]エラー情報を取得するレコードの 0 から始まる番号。  
  
 `lcid`  
 [in]返されるエラー情報のロケール ID。  
  
 `pbstrDescription`  
 [out]エラーまたはロケールはサポートされていない場合は NULL のテキストの説明へのポインター。 「解説」を参照してください。  
  
 `pbstrSource`  
 [out]エラーを生成したコンポーネントの名前を含む文字列へのポインター。  
  
 `pguid`  
 [out]エラーを定義するインターフェイスの GUID へのポインター。  
  
 *pdwHelpContext*  
 [out]エラーのヘルプ コンテキスト ID へのポインター。  
  
 *pbstrHelpFile*  
 [out]エラーを説明するヘルプ ファイルへのパスを含む文字列へのポインター。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は、`S_OK`。 参照してください[IErrorRecords::GetErrorInfo](https://msdn.microsoft.com/en-us/library/ms711230.aspx)で、 *OLE DB プログラマーズ リファレンス*の他の戻り値。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="remarks"></a>コメント  
 出力値`pbstrDescription`呼び出し ierrorinfo::getdescription、ロケールがサポートされていない場合、または、次の条件の両方に該当する場合、値を NULL に設定するによって内部的に取得されます。  
  
1.  値`lcid`米国ではありません英語と  
  
2.  値`lcid`は GetUserDefaultLCID によって返される値と等しくないです。  
  
## <a name="see-also"></a>参照  
 [CDBErrorInfo クラス](../../data/oledb/cdberrorinfo-class.md)