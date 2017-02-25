---
title: "WSADATA 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WSADATA"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WSADATA 構造体"
ms.assetid: 80cc60e5-f9ae-4290-8ed5-07003136627d
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# WSADATA 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`WSADATA` 構造体は `AfxSocketInit` のグローバル関数の呼び出しによって返されるストア ウィンドウのソケット初期化情報に使用されます。  
  
## 構文  
  
```  
  
      struct WSAData {  
   WORD wVersion;  
   WORD wHighVersion;  
   char szDescription[WSADESCRIPTION_LEN+1];  
   char szSystemStatus[WSASYSSTATUS_LEN+1];  
   unsigned short iMaxSockets;  
   unsigned short iMaxUdpDg;  
   char FAR * lpVendorInfo;  
};  
```  
  
#### パラメーター  
 *wVersion*  
 Windows ソケット DLL が呼び出し元が使用できるようにします。Windows ソケットの固有のバージョン。  
  
 *wHighVersion*  
 このサポート DLL ができる Windows ソケット固有の最上位バージョン \(上の例として、エンコードされて\)。  通常、これは **wVersion**と同じです。  
  
 *szDescription*  
 Windows ソケット DLL が Windows ソケットの実装の説明をコピーした販売元の ID を含む null で終わるな ASCII 文字列。  テキスト \(長さが 256 文字まで\) はコントロールと書式指定文字が含まれるように対する警告されます文字、販売元を含めることができますが、: アプリケーションがこれを配置する最も一般的な用途は、ステータス メッセージで \(通常は切り捨てられる\) を表示することです。  
  
 *szSystemStatus*  
 Windows ソケット DLL が関連するステータスまたは構成情報をコピーする null で終わるな ASCII 文字列。  Windows ソケット DLL は、情報のユーザーまたはサポート スタッフに便利な場合があります。場合のみ、このフィールドを使用する必要があります; これは **szDescription** フィールドの拡張と見なされることはありません。  
  
 *iMaxSockets*  
 一つのプロセス内に、開くできるソケットの最大数。  Windows ソケットの実装は、プロセスへの割り当てのソケット グローバル プールを提供する; \/p に、ソケットのプロセスごとのリソースを割り当てることができます。  数値は、Windows ソケット DLL またはネットワーク ソフトウェアが設定された方法を反映できます。  アプリケーションの作成者は粗野に示す値として Windows ソケットの実装がアプリケーションで使用できるかどうかをこの数を指定できます。  たとえば、X の Windows サーバーが最初に起動されたとき **iMaxSockets** を調べる可能性があります: それ以外の 8 未満の場合、アプリケーションはネットワーク ソフトウェアを再構成するようにユーザーに指示するエラー メッセージが表示されます。これは **szSystemStatus** のテキストが使用される場合があります\)。マニフェストに使用されている他の Windows ソケットのアプリケーションが存在する可能性があるため、特定のアプリケーションを実際に **iMaxSockets** ソケットを割り当てることができるという保証はありません。  
  
 *iMaxUdpDg*  
 Windows ソケットのアプリケーションで送信または受信できるユーザー データグラム プロトコル \(UDP\) の最大データグラムのサイズ \(バイト単位\)。  実装が制限を課さなければ、**iMaxUdpDg** はゼロです。  Berkeley ソケットの多くの実装では、必要に応じて断片化\) の 8192 バイトの暗黙の制限が UDP "データグラムです。  たとえば、Windows ソケットの実装は、フラグメントの再組立てバッファーの割り当てに基づいて制限を課すことができます。  準拠の Windows ソケットの実装の **iMaxUdpDg** の最小値は 512 です。  **iMaxUdpDg**の値に関係なく、ネットワークの最大伝送単位 \(MTU\) より大きいブロードキャストのデータグラムを送信するようにするには、この方法であることに注意してください。\(MTU を検出するために、Windows ソケット API の機能を提供しない 512 バイト以下である必要があります\)。  
  
 *lpVendorInfo*  
 ベンダー固有のデータ構造に far ポインター。   \(指定されている場合\) は、この構造体の定義は、Windows ソケットの固有の対象外です。  
  
> [!NOTE]
>  MFC では、`WSADATA` 構造体は、`InitInstance` 関数で呼び出す `AfxSocketInit` 関数によって返されます。  そこから情報を使用する必要がある場合は、構造体を取得し、プログラムでも格納できます。  
  
## 必要条件  
 **ヘッダー:** winsock2.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [AfxSocketInit](../Topic/AfxSocketInit.md)