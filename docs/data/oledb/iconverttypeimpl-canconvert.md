---
title: "IConvertTypeImpl::CanConvert | Microsoft Docs"
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
  - "IConvertTypeImpl.CanConvert"
  - "CanConvert"
  - "IConvertTypeImpl::CanConvert"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanConvert メソッド"
ms.assetid: bdad6e95-bc0b-4427-9b5e-eea51f09f392
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IConvertTypeImpl::CanConvert
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コマンドと行セットの型変換の可用性の情報を提供します。  
  
## 構文  
  
```  
  
      STDMETHOD(CanConvert)(   
   DBTYPE wFromType,   
   DBTYPE wToType,   
   DBCONVERTFLAGS dwConvertFlags    
);  
```  
  
#### パラメーター  
 *OLE DB Programmer's Reference*の [IConvertType::CanConvert](https://msdn.microsoft.com/en-us/library/ms711224.aspx) を参照してください。  
  
## 解説  
 `MSADC.DLL`の OLE DB のデータ変換。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IConvertTypeImpl クラス](../../data/oledb/iconverttypeimpl-class.md)