---
title: "CAtlFileMappingBase クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CAtlFileMappingBase"
  - "ATL::CAtlFileMappingBase"
  - "CAtlFileMappingBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlFileMappingBase クラス"
ms.assetid: be555723-2790-4f57-a8fb-be4d68460775
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CAtlFileMappingBase クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、メモリ マップト ファイルを表します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CAtlFileMappingBase  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAtlFileMappingBase::CAtlFileMappingBase](../Topic/CAtlFileMappingBase::CAtlFileMappingBase.md)|コンストラクターです。|  
|[CAtlFileMappingBase::~CAtlFileMappingBase](../Topic/CAtlFileMappingBase::~CAtlFileMappingBase.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAtlFileMappingBase::CopyFrom](../Topic/CAtlFileMappingBase::CopyFrom.md)|ファイル マップ オブジェクトからコピーする場合は、このメソッドを呼び出します。|  
|[CAtlFileMappingBase::GetData](../Topic/CAtlFileMappingBase::GetData.md)|ファイル マップ オブジェクトからデータを取得するときにこのメソッドを呼び出します。|  
|[CAtlFileMappingBase::GetHandle](../Topic/CAtlFileMappingBase::GetHandle.md)|ファイル ハンドルを返すには、このメソッドを呼び出します。|  
|[CAtlFileMappingBase::GetMappingSize](../Topic/CAtlFileMappingBase::GetMappingSize.md)|ファイル マップ オブジェクトからマップ サイズを取得するときにこのメソッドを呼び出します。|  
|[CAtlFileMappingBase::MapFile](../Topic/CAtlFileMappingBase::MapFile.md)|ファイル マップ オブジェクトを作成するには、このメソッドを呼び出します。|  
|[CAtlFileMappingBase::MapSharedMem](../Topic/CAtlFileMappingBase::MapSharedMem.md)|すべてのプロセスへのフル アクセスを許可するファイル マップ オブジェクトを作成するには、このメソッドを呼び出します。|  
|[CAtlFileMappingBase::OpenMapping](../Topic/CAtlFileMappingBase::OpenMapping.md)|ファイル マップ オブジェクトへのハンドルを返すには、このメソッドを呼び出します。|  
|[CAtlFileMappingBase::Unmap](../Topic/CAtlFileMappingBase::Unmap.md)|マップ解除するには、このメソッドをファイル マップ オブジェクトで呼び出します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CAtlFileMappingBase::operator \=](../Topic/CAtlFileMappingBase::operator%20=.md)|別のファイル マップ オブジェクトに対する現在のファイル マップ オブジェクトを設定します。|  
  
## 解説  
 マッピング ファイルは、プロセスの仮想アドレス空間内の部分と、ファイルの内容の関連です。  このクラスは、プログラムでデータを簡単にアクセスできるようにする、共有ファイル マップ オブジェクトを作成するメソッドを提供します。  
  
 詳細については、[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]の [ファイル マップ](http://msdn.microsoft.com/library/windows/desktop/aa366556) を参照してください。  
  
## 必要条件  
 **ヘッダー :** atlfile.h  
  
## 参照  
 [CAtlFileMapping クラス](../Topic/CAtlFileMapping%20Class.md)   
 [クラスの概要](../../atl/atl-class-overview.md)