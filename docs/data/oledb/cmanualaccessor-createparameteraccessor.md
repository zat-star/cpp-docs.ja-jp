---
title: "CManualAccessor::CreateParameterAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CManualAccessor::CreateParameterAccessor"
  - "ATL.CManualAccessor.CreateParameterAccessor"
  - "CManualAccessor.CreateParameterAccessor"
  - "CreateParameterAccessor"
  - "CManualAccessor::CreateParameterAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateParameterAccessor メソッド"
ms.assetid: d0a2095b-b37c-4472-accc-45ef365a18c8
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CManualAccessor::CreateParameterAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

バインド パラメーターのメモリを構築し、初期化しますパラメーター データ メンバーを割り当てます。  
  
## 構文  
  
```  
  
      HRESULT CreateParameterAccessor(   
   int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize    
) throw( );  
```  
  
#### パラメーター  
 `nBindEntries`  
 \[\]列数。  
  
 `pBuffer`  
 \[\]入力列が格納されるバッファーへのポインター。  
  
 `nBufferSize`  
 \[\]バッファーのサイズ \(バイト数\)  
  
## 戻り値  
 `HRESULT` 標準値のいずれか 1 つが。  
  
## 解説  
 [AddParameterEntry](../Topic/CManualAccessor::AddParameterEntry.md)を呼び出す前にこの関数を呼び出す必要があります。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CManualAccessor クラス](../Topic/CManualAccessor%20Class.md)   
 [CManualAccessor::CreateAccessor](../Topic/CManualAccessor::CreateAccessor.md)   
 [CManualAccessor::AddParameterEntry](../Topic/CManualAccessor::AddParameterEntry.md)