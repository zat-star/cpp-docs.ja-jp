---
title: "CAtlFile クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAtlFile"
  - "ATL::CAtlFile"
  - "ATL.CAtlFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAtlFile クラス"
ms.assetid: 93ed160b-af2a-448c-9cbe-e5fa46c199bb
caps.latest.revision: 23
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlFile クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスは、Windows のファイル処理 API の Thin ラッパーを提供します。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
class CAtlFile : public CHandle  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAtlFile::CAtlFile](../Topic/CAtlFile::CAtlFile.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAtlFile::Create](../Topic/CAtlFile::Create.md)|新しいファイルを作成するか、またはファイルを開きます。|  
|[CAtlFile::Flush](../Topic/CAtlFile::Flush.md)|ファイル用のバッファーをクリアし、バッファーに格納されていたすべてのデータをファイルに書き込みます。|  
|[CAtlFile::GetOverlappedResult](../Topic/CAtlFile::GetOverlappedResult.md)|ファイルに対する重複操作の結果を取得します。|  
|[CAtlFile::GetPosition](../Topic/CAtlFile::GetPosition.md)|ファイルから現在のファイル ポインター位置を取得します。|  
|[CAtlFile::GetSize](../Topic/CAtlFile::GetSize.md)|バイト単位のファイル サイズを取得します。|  
|[CAtlFile::LockRange](../Topic/CAtlFile::LockRange.md)|ファイル内の特定の領域をロックして、ほかのプロセスがアクセスできないようにします。|  
|[CAtlFile::Read](../Topic/CAtlFile::Read.md)|ファイル ポインターが示す位置を開始位置として、ファイルのデータを読み取ります。|  
|[CAtlFile::Seek](../Topic/CAtlFile::Seek.md)|ファイル内のファイル ポインターの位置へ移動します。|  
|[CAtlFile::SetSize](../Topic/CAtlFile::SetSize.md)|ファイル サイズを設定します。|  
|[CAtlFile::UnlockRange](../Topic/CAtlFile::UnlockRange.md)|ファイルの領域のロックを解除します。|  
|[CAtlFile::Write](../Topic/CAtlFile::Write.md)|ファイル ポインターが示す位置を開始位置として、ファイルにデータを書き込みます。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAtlFile::m\_pTM](../Topic/CAtlFile::m_pTM.md)|`CAtlTransactionManager` のオブジェクトへのポインター。|  
  
## 解説  
 Windows API は MFC の依存関係を指定せずに使用した場合、必要なニーズをファイルを処理するときにこのクラスを比較的簡単ですが、多くの抽象化使用します。  
  
## 継承階層  
 [CHandle](../../atl/reference/chandle-class.md)  
  
 `CAtlFile`  
  
## 必要条件  
 **ヘッダー :** atlfile.h  
  
## 参照  
 [Marquee サンプル](../../top/visual-cpp-samples.md)   
 [クラスの概要](../../atl/atl-class-overview.md)   
 [CHandle クラス](../../atl/reference/chandle-class.md)