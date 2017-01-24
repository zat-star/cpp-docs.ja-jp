---
title: "CArchive クラス | Microsoft Docs"
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
  - "CArchive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive クラス"
  - "データ ストレージ [C++], CArchive クラス"
  - "I/O [MFC], アーカイブ オブジェクト"
  - "シリアル化 [C++], CArchive クラス"
  - "ストレージ [C++], CArchive クラス"
ms.assetid: 9e950d23-b874-456e-ae4b-fe00781a7699
caps.latest.revision: 21
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CArchive クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

割り当てこれらのオブジェクトを削除した後も保持する永続的なバイナリ形式 \(通常はディスク ストレージ\) オブジェクトの複雑なネットワークを保存できます。  
  
## 構文  
  
```  
class CArchive  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CArchive::CArchive](../Topic/CArchive::CArchive.md)|`CArchive` オブジェクトを作成します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CArchive::Abort](../Topic/CArchive::Abort.md)|例外をスローせずに、アーカイブを閉じます。|  
|[CArchive::Close](../Topic/CArchive::Close.md)|書き込まれていないデータをフラッシュし、`CFile` から切り離します。|  
|[CArchive::Flush](../Topic/CArchive::Flush.md)|書き込まれていないデータをアーカイブ バッファーからフラッシュします。|  
|[CArchive::GetFile](../Topic/CArchive::GetFile.md)|このアーカイブの `CFile` オブジェクト ポインターを取得します。|  
|[CArchive::GetObjectSchema](../Topic/CArchive::GetObjectSchema.md)|`Serialize` 関数から呼び出して、逆シリアル化されているオブジェクトのバージョンを判断します。|  
|[CArchive::IsBufferEmpty](../Topic/CArchive::IsBufferEmpty.md)|Windows ソケットの受信プロセス中に、バッファーが空になったかどうかを判断します。|  
|[CArchive::IsLoading](../Topic/CArchive::IsLoading.md)|アーカイブが読み込み中かどうかを判断します。|  
|[CArchive::IsStoring](../Topic/CArchive::IsStoring.md)|アーカイブが格納中かどうかを判断します。|  
|[CArchive::MapObject](../Topic/CArchive::MapObject.md)|ファイルにシリアル化せず、参照へのサブオブジェクトとして使用できるオブジェクトをマップに配置します。|  
|[CArchive::Read](../Topic/CArchive::Read.md)|生バイトを読み込みます。|  
|[CArchive::ReadClass](../Topic/CArchive::ReadClass.md)|`WriteClass` で既に格納されているクラス参照を読み込みます。|  
|[CArchive::ReadObject](../Topic/CArchive::ReadObject.md)|オブジェクトの `Serialize` 関数を呼び出して読み込みます。|  
|[CArchive::ReadString](../Topic/CArchive::ReadString.md)|テキストを 1 行読み込みます。|  
|[CArchive::SerializeClass](../Topic/CArchive::SerializeClass.md)|`CArchive` の方向に応じて、クラス参照を `CArchive` オブジェクトへ読み込み、または書き込みます。|  
|[CArchive::SetLoadParams](../Topic/CArchive::SetLoadParams.md)|読み込み配列の拡張に応じて、サイズを設定します。  オブジェクトは、読み込まれたか、または `MapObject``ReadObject` を呼び出す前に呼び出す必要があります。|  
|[CArchive::SetObjectSchema](../Topic/CArchive::SetObjectSchema.md)|アーカイブ オブジェクトに格納されているオブジェクト スキーマを設定します。|  
|[CArchive::SetStoreParams](../Topic/CArchive::SetStoreParams.md)|シリアル化プロセス中に、一意のオブジェクトを識別するマップのハッシュ テーブルのサイズおよびブロック サイズを設定します。|  
|[CArchive::Write](../Topic/CArchive::Write.md)|生バイトを書き込みます。|  
|[CArchive::WriteClass](../Topic/CArchive::WriteClass.md)|`CRuntimeClass` への参照を `CArchive` へ書き込みます。|  
|[CArchive::WriteObject](../Topic/CArchive::WriteObject.md)|オブジェクトの `Serialize` 関数を呼び出して格納します。|  
|[CArchive::WriteString](../Topic/CArchive::WriteString.md)|テキストを 1 行書き込みます。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CArchive::operator \<\<](../Topic/CArchive::operator%20%3C%3C.md)|オブジェクトとプリミティブ型をアーカイブに格納します。|  
|[CArchive::operator \>\>](../Topic/CArchive::operator%20%3E%3E.md)|オブジェクトとプリミティブ型をアーカイブから読み込みます。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CArchive::m\_pDocument](../Topic/CArchive::m_pDocument.md)||  
  
## 解説  
 `CArchive` には、基本クラスはありません。  
  
 後でメモリの内容を再構成する永続ストレージからオブジェクトを読み込むことができます。  データを永続化するこのプロセスが呼び出されます」。と「シリアル化  
  
 種類のバイナリ ストリームとしてアーカイブ オブジェクトと考えることができます。  入出力ストリームのように、アーカイブは、ファイルに関連付けられ、ストレージに対する読み取りと書き込みバッファー データができます。  ASCII 文字の入出力ストリームのプロセス シーケンスが、アーカイブが有効で、非詳細な形式のバイナリ オブジェクト データを処理します。  
  
 `CArchive` のオブジェクトを作成するに [CFile](../../mfc/reference/cfile-class.md) のオブジェクトを作成する必要があります。  また、アーカイブの読み込み\/ストアの状態がファイルのオープン モードと互換性があることを確認する必要があります。  ファイルごとに 1 回のアクティブなアーカイブに制限されます。  
  
 `CArchive` のオブジェクトを構築するときに、開いているファイルを表す派生クラス\) またはクラス `CFile` のオブジェクトにアタッチします \(。  アーカイブが読み込むまたは格納に使用されるかどうかも指定します。  `CArchive` のオブジェクトは、基本型でのみ処理できますが、[CObject](../Topic/CObject%20Class.md)\-シリアル化用にデザインされた派生クラスのオブジェクト。  シリアル化可能なクラスには、通常、`Serialize` のメンバー関数を持ち、通常、クラス `CObject`の下に説明されているように [DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md) と [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md) のマクロを使用します。  
  
 オーバーロードされた挿入**\>\>** \(抽出\) および \(**\<\<**\) 演算子は、両方のプリミティブ型と `CObject`派生クラスをサポートするための便利なアーカイブのプログラミング インターフェイスです。  
  
 `CArchive` は、MFC Windows ソケットのクラス [CSocket](../../mfc/reference/csocket-class.md) と [CSocketFile](../Topic/CSocketFile%20Class.md)とのプログラミングをサポートしています。  [IsBufferEmpty](../Topic/CArchive::IsBufferEmpty.md) のメンバー関数のサポートを使用します。  
  
 `CArchive`の詳細については、" " [&#91;シリアル化&#93;](../Topic/Serialization%20in%20MFC.md) と [Windows ソケット: アーカイブを持つソケットを使用する](../../mfc/windows-sockets-using-sockets-with-archives.md)を参照してください。  
  
## 継承階層  
 `CArchive`  
  
## 必要条件  
 **ヘッダー:** afx.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [CObject クラス](../Topic/CObject%20Class.md)   
 [CSocket クラス](../../mfc/reference/csocket-class.md)   
 [CSocketFile クラス](../Topic/CSocketFile%20Class.md)