---
title: "Windows ソケット : アーカイブ付きソケットの動作 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ソケット [C++], 同期操作"
  - "ソケット [C++], アーカイブを使用する"
  - "同期状態ソケット"
  - "2 つの状態のソケット オブジェクト"
  - "Windows ソケット [C++], 同期の"
  - "Windows ソケット [C++], アーカイブを使用する"
ms.assetid: d8ae4039-391d-44f0-a19b-558817affcbb
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows ソケット : アーカイブ付きソケットの動作
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、Windows ソケットを通じてデータを送受信できるを簡単にするために [CSocket](../mfc/reference/csocket-class.md) オブジェクト、[CSocketFile](../Topic/CSocketFile%20Class.md) オブジェクトと [CArchive](../mfc/reference/carchive-class.md) オブジェクトを結合する方法を示しています。  
  
 記事 [Windows ソケット: アーカイブを使用してソケットの例](../mfc/windows-sockets-example-of-sockets-using-archives.md) は **PacketSerialize** 関数を示します。  アーカイブ オブジェクトと同様に **PacketSerialize** 例の作業のアーカイブ オブジェクトは、MFC [シリアル化する](../Topic/CObject::Serialize.md) 関数に渡されました。  必要な違いは [CFile](../mfc/reference/cfile-class.md) の標準オブジェクト \(通常はディスク上のファイルに関連付けられた\) `CSocketFile` オブジェクトにソケットの場合、アーカイブ関連していません。  ディスク ファイルに接続するのではなく、`CSocketFile` オブジェクトは `CSocket` にオブジェクトを追加します。  
  
 `CArchive` オブジェクトはバッファーを管理します。  保存 \(送信\) のアーカイブ バッファーが完了すると、`CFile` 関連のオブジェクトは、バッファーの内容を書き込みます。  ソケットに接続されているアーカイブのバッファーをフラッシュするとメッセージの送信に相当します。  読み込み \(~\) のアーカイブ バッファーが完了すると、`CFile` オブジェクトはバッファーが再び使用できるようになるまで読み取りを停止します。  
  
 クラス `CSocketFile` は `CFile`から派生しますが、関数の位置 \(`Seek`、`GetLength`、`SetLength`など\)、Lock 関数 \(`LockRange`、`UnlockRange`\)、または `GetPosition` 関数など [CFile](../mfc/reference/cfile-class.md) メンバー関数をサポートしていません。  [CSocketFile](../Topic/CSocketFile%20Class.md) のすべてのオブジェクトが書き込みにするか、バイト シーケンスを関連する `CSocket` とからの読み取りに使用します。  ファイルが複雑ではないため、`Seek` などの操作と `GetPosition` は意味がありません。  `CSocketFile` は `CFile`から派生されます。そのため、通常、これらのメンバー関数すべてを継承します。  これを回避するには、`CFile` でサポートされていないメンバー関数は `CSocketFile` で [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)をスローするようにようにオーバーライドされます。  
  
 `CSocket` の `CSocketFile` オブジェクトの呼び出しのメンバー関数は、データを送受信されたに変更します。  
  
 次の図は、通信の両側でこれらのオブジェクト間の関係を示します。  
  
 ![CArchive、CSocketFile、CSocket](../Image/vc38IA1.gif "vc38IA1")  
CArchive、CSocketFile、CSocket  
  
 この Express 複雑さの目的は、ソケット詳細の管理のニーズから独自保護することです。  ソケット サポート、およびアーカイブ ファイルを作成し、それをアーカイブに挿入するか、アーカイブから取得することによってデータを送信または受信します。  [CArchive](../mfc/reference/carchive-class.md)、[CSocketFile](../Topic/CSocketFile%20Class.md)と [CSocket](../mfc/reference/csocket-class.md) に詳細が背後で管理します。  
  
 `CSocket` オブジェクトは実際に 2 状態オブジェクトです:、\(通常の状態\) 非同期および場合に同期できます。  非同期状態で、ソケットはフレームワークから非同期の通知を受け取ることができます。  ただし、データにソケットを受け取り、または送信などの操作中に同期になります。  これにより、同期操作が完了するまで、ソケットでそのほかの非同期の通知を受け取ることを意味します。  これはモードを切り替えるため、たとえば次のようなものができます。:  
  
 [!CODE [NVC_MFCSimpleSocket#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCSimpleSocket#2)]  
  
 `CSocket` が 2 状態オブジェクトとして実装されなかったら、前の通知を処理中にイベントの同じ種類の追加の通知を受け取ることができる場合があります。  たとえば `OnReceive`の処理中に、`OnReceive` の通知を受け取ることがあります。  上記のコードでは、アーカイブから `str` を取得するには、再帰を招く可能性があります。  状態を変更することによって、`CSocket` は追加通知を防ぐことで、再帰を防ぎます。  一般的な規則では通知内の通知ではありません。  
  
> [!NOTE]
>  `CSocketFile` は、`CArchive` オブジェクトなしで a \(制限付き\) ファイルを使用できます。  既定では、`CSocketFile` のコンストラクターの `bArchiveCompatible` パラメーター **TRUE**です。  これは、ファイルがアーカイブ オブジェクトで使用されることを指定します。  アーカイブのないファイル オブジェクトを使用するには、`bArchiveCompatible` パラメーターの **FALSE** を渡します。  
  
 「アーカイブ」互換モードでは、`CSocketFile` オブジェクトは、より優れたパフォーマンスを実現し、軽減「デッドロックの危険性を」デッドロックが送信と受信ソケットが互いに待機している、またはと発生し、共通のリソースを待機します。  この状況は `CSocketFile` を使用する `CArchive` オブジェクト `CFile` オブジェクト方法と発生する場合があります。  `CFile`を使用すると、アーカイブは少量のバイトを超える場合は、ファイルの終端に達した場合は到達した要求したと判断できます。  ただし、`CSocketFile`してデータは、メッセージが; バッファーは、要求されたバイト数が、ファイルの終端を意味するよりも少ないため、複数のメッセージを受け取ることができます。  アプリケーションは、バッファーが空になるまで `CFile`が上がる可能性がある、バッファーからのメッセージの読み取り続行できるようにこの場合に実行します。  `CArchive` の [IsBufferEmpty](../Topic/CArchive::IsBufferEmpty.md) 関数はアーカイブのバッファーの状態をこのような場合には監視するのに役立ちます。  
  
 詳細については、[Windows ソケット: アーカイブが持つソケットを使用する](../mfc/windows-sockets-using-sockets-with-archives.md)を参照します  
  
## 参照  
 [MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)   
 [CObject::Serialize](../Topic/CObject::Serialize.md)