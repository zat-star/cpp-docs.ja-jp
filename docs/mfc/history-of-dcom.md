---
title: "DCOM の歴史 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Remote Automation, DCOM
- DCOM, about DCOM
- DCOM
ms.assetid: c21aa0ea-1396-4b52-b77f-88fb0fdd2a5c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9e5607fd240c7a97691189b8a3afa5e7c0171e26
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="history-of-dcom"></a>DCOM の歴史
オートメーションは、1993 年前半で初めて導入されました、ときに、同じコンピューターで実行されるアプリケーション間でのみ使用されていることでした。 ただし、OLE とは、COM (コンポーネント オブジェクト モデル) の残りの部分として同じ基盤を共有しているので、常に意図されたことになった「リモート」リモート処理機能を含む COM 自体が更新されたとき。 純粋なローカル操作から分散操作への移行は、既存のコードをほとんどまたはまったく変更することも予定だった。  
  
 「リモート」どういうローカル COM インターフェイスのコンシューマーが存在する使用されるようにし、そのインターフェイスのプロバイダーと同じコンピューター上で実行します。 たとえば、Microsoft Visual Basic は、デスクトップ コンピューターに Microsoft Excel のコピーを制御でしたが、別のコンピューターで Excel の実行を指示することができません。 分散 COM の開発、インターフェイスのコンシューマーはインターフェイス プロバイダーが実行されるものと同じコンピューター上に存在する必要はなくなります。  
  
 COM が複数のネットワークを使用するために適合すると、一度インターフェイスをローカル実行モデルが関連付けられていない (ローカル コンピューターの機能依存の固有のいくつかのインターフェイスであるなど図面はインターフェイスのメソッドとしてデバイス コンテキストへのハンドルがあります。パラメーター) には、分散機能があります。 インターフェイス コンシューマーは特定のインターフェイスの要求を作成します。別のコンピューターでは、(または実行する) を実行しているオブジェクトのインスタンスによってそのインターフェイスを提供することがあります。 COM 内の配布メカニズムでは、コンシューマーはように、プロバイダーに接続するコンシューマーによって行われたメソッドの呼び出しが表示されますプロバイダー最後に、実行する場所です。 戻り値は、コンシューマーに送信されます。 あらゆる点で、配布の動作は、コンシューマーとプロバイダーの両方に対して透過的です。  
  
 このようなさまざまな COM が存在しています。 ("分散 COM") の DCOM のバージョンの Windows NT バージョン 4.0 以降およびなどの Windows 2000 が付属しています。 1996 年後半以降がも経過している Windows 9x の使用可能な x。 どちらの場合は、DCOM は置換機能とその他の Dll のセットを一部のユーティリティでは、ローカルおよびリモートの両方の COM 機能を提供で構成します。 これで、Win32 ベースのプラットフォームでは、部分で固有であるためと、使用可能になる他のプラットフォームで他の組織で時間の経過と共にします。  
  
## <a name="in-this-section"></a>このセクションの内容  
 [ここではリモート オートメーションを使用](where-does-remote-automation-fit-in-q.md)  
  
 [どのようなリモート オートメーションを管轄します。](what-does-remote-automation-provide-q.md)  
  
## <a name="see-also"></a>関連項目  
 [リモート オートメーション](../mfc/remote-automation.md)
