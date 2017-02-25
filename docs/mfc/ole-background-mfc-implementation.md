---
title: "OLE の背景知識 : MFC における実装 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IMarshall"
  - "IMoniker"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IMarshall クラス"
  - "IMoniker インターフェイス, MFC"
  - "MFC ライブラリ, 実装"
  - "OLE IMarshal インターフェイス"
  - "OLE IMoniker インターフェイス"
  - "OLE IUnknown"
  - "OLE MFC ライブラリの実装"
  - "OLE, 複合ファイル"
ms.assetid: 2b67016a-d78e-4d60-925f-c28ec8fb6180
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# OLE の背景知識 : MFC における実装
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

生の OLE API のサイズが大きく複雑であるため、OLE アプリケーションを作成するために直接呼び出すことは非常に時間がかかります。  OLE の Microsoft Foundation Class ライブラリの実装の目的は、OLE 可能なアプリケーションを作成するための機能を備えたする必要がある作業量を単純化するです。  
  
 ここでは、ずっと実装された内部 MFC ではなく OLE API の一部を示しています。  説明は、実装されたマップは [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の OLE セクションにに何方法について説明します。  
  
##  <a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a> クラス ライブラリにより実装されない OLE の部分  
 OLE のインターフェイスと機能は、MFC によって直接提供されません。  これらの機能を使用する場合は、OLE API を直接呼び出すこともできます。  
  
 IMoniker インターフェイス  
 `IMoniker` インターフェイスはクラス ライブラリで \(たとえば、`COleServerItem` クラス\) 実装されましたり、プログラマに前にさらされていなかった。  このインターフェイスの詳細については、[!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]の OLE セクションの OLE モニカーの実装を参照します。  ただし、クラス [CMonikerFile](../Topic/CMonikerFile%20Class.md) と [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)"も参照してください。  
  
 IUnknown と IMarshal インターフェイス  
 **IUnknown** インターフェイス、クラス ライブラリにより実装されますが、プログラマには公開されません。  **IMarshal** インターフェイス、クラス ライブラリにより実装されませんが、内部的に使用されます。  クラス ライブラリを使用して構築されたオートメーション サーバーに既に構築されたマーシャリング機構があります。  
  
 Docfiles \(複合ファイル\)  
 複合ファイルはクラス ライブラリで部分的にサポートされます。  直接作成を超える複合ファイルを処理する関数のいずれもサポートされません。  MFC は、標準のファイル内の関数のストリームの操作をサポートするために **COleFileStream** クラスを使用します。  詳細については、記事 [コンテナー: 複合ファイル](../mfc/containers-compound-files.md)を参照します。  
  
 インプロセス サーバー オブジェクトおよびハンドラー  
 インプロセス サーバー オブジェクトおよびハンドラーはダイナミック リンク ライブラリ \(DLL\) のビジュアル編集のデータまたはフル コンポーネント オブジェクト モデルの \(COM\) オブジェクトの実装を有効にします。  これを行うには、OLE API を直接呼び出すことによって、DLL を実装できます。  ただし、オートメーション サーバーの作成、サーバーにユーザー インターフェイスがない場合は、サーバーをインプロセス サーバーに、DLL に完全に組み込むために AppWizard を使用できます。  これらのトピックの詳細については、「[オートメーション サーバー](../mfc/automation-servers.md)」を参照してください。  
  
> [!TIP]
>  オートメーション サーバーを実装する最も簡単な方法は、DLL に配置することです。  MFC はこの方法がサポートされます。  
  
 Microsoft OLE の基本クラスが OLE インターフェイスをどのように実装するか詳細については、MFC のテクニカル ノート [38](../mfc/tn038-mfc-ole-iunknown-implementation.md)、[39](../mfc/tn039-mfc-ole-automation-implementation.md)と [40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md)を参照します。  
  
## 参照  
 [OLE の背景知識](../mfc/ole-background.md)   
 [OLE の背景知識 : 実装の方法](../mfc/ole-background-implementation-strategies.md)