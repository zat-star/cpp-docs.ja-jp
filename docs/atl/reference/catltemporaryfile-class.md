---
title: "CAtlTemporaryFile クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAtlTemporaryFile"
  - "ATL.CAtlTemporaryFile"
  - "ATL::CAtlTemporaryFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlTemporaryFile クラス"
ms.assetid: 05f0f2a5-94f6-4594-8dae-b114292ff5f9
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CAtlTemporaryFile クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、一時ファイルを作成および使用するためのメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CAtlTemporaryFile  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAtlTemporaryFile::CAtlTemporaryFile](../Topic/CAtlTemporaryFile::CAtlTemporaryFile.md)|コンストラクターです。|  
|[CAtlTemporaryFile::~CAtlTemporaryFile](../Topic/CAtlTemporaryFile::~CAtlTemporaryFile.md)|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAtlTemporaryFile::Close](../Topic/CAtlTemporaryFile::Close.md)|一時ファイルの内容を削除するか、指定したファイル名の下に格納する閉じるようにこのメソッドを呼び出します。|  
|[CAtlTemporaryFile::Create](../Topic/CAtlTemporaryFile::Create.md)|一時ファイルを作成するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::Flush](../Topic/CAtlTemporaryFile::Flush.md)|一時ファイルに書き込むファイル バッファー内の残りのデータを強制的にこのメソッドを呼び出します。|  
|[CAtlTemporaryFile::GetPosition](../Topic/CAtlTemporaryFile::GetPosition.md)|現在のファイル ポインターの位置を取得するときにこのメソッドを呼び出します。|  
|[CAtlTemporaryFile::GetSize](../Topic/CAtlTemporaryFile::GetSize.md)|一時ファイルのサイズをバイト単位で取得するときにこのメソッドを呼び出します。|  
|[CAtlTemporaryFile::HandsOff](../Topic/CAtlTemporaryFile::HandsOff.md)|`CAtlTemporaryFile` のオブジェクトからのファイルの関連付けを解除するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::HandsOn](../Topic/CAtlTemporaryFile::HandsOn.md)|既存の一時ファイルを開き、ファイルの末尾にポインターを設定するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::LockRange](../Topic/CAtlTemporaryFile::LockRange.md)|ファイル内の特定の領域をロックして、ほかのプロセスがアクセスできないようにします。|  
|[CAtlTemporaryFile::Read](../Topic/CAtlTemporaryFile::Read.md)|ファイル ポインターが示す位置を開始する一時ファイルからデータを読み取るために、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::Seek](../Topic/CAtlTemporaryFile::Seek.md)|一時ファイルのファイル ポインターを実行するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::SetSize](../Topic/CAtlTemporaryFile::SetSize.md)|一時ファイルのサイズを設定するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::TempFileName](../Topic/CAtlTemporaryFile::TempFileName.md)|一時ファイルの名前を返すには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::UnlockRange](../Topic/CAtlTemporaryFile::UnlockRange.md)|一時ファイルの領域のロックを解除するには、このメソッドを呼び出します。|  
|[CAtlTemporaryFile::Write](../Topic/CAtlTemporaryFile::Write.md)|ファイル ポインターが示す位置を開始する一時ファイルにデータを書き込むためにこのメソッドを呼び出します。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CAtlTemporaryFile::operator HANDLE](../Topic/CAtlTemporaryFile::operator%20HANDLE.md)|一時ファイルのハンドルを返します。|  
  
## 解説  
 `CAtlTemporaryFile` は一時ファイルを作成し、使用するのは簡単です。  ファイルが自動的に表示され、閉じて開き、および削除されます。  ファイルが終了した後、ファイルの内容が必要な場合は、指定した名前で新しいファイルに保存できます。  
  
## 必要条件  
 **ヘッダー :** atlfile.h  
  
## 使用例  
 [CAtlTemporaryFile::CAtlTemporaryFile](../Topic/CAtlTemporaryFile::CAtlTemporaryFile.md)の例を参照してください。  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CAtlFile クラス](../../atl/reference/catlfile-class.md)