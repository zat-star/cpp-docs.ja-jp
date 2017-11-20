---
title: "リモート オートメーションを使用する場合 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: Remote Automation, DCOM
ms.assetid: 4c4c8176-cfc0-44f7-bc87-b690f069ad2f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 101d34c9ed610cb375c0755e7698f45a1b16e935
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="where-does-remote-automation-fit-in"></a>リモート オートメーションを使用する場合
DCOM は 1996 年にリリースされたおよびは 32 ビットおよび 64 ビット プラットフォームのみで使用できます。 Microsoft Visual Basic チームでは、オートメーションを使用して通信するためにそのコンポーネントを許可すると Visual Basic を考えるが常にします。 分散型バージョンなどの深刻な制限されているエンタープライズ環境でこれらの機能の使用をため、オートメーション用のリモート処理コンポーネントの独自セットの作成を調査するために Visual Basic 4.0 Enterprise Edition の開発チームが決定されましたOLE と COM の部分 明確に、主な目標は、利用可能になったときに、DCOM によって置き換えることが、結果と互換性があることを確認することでした。 前に、16 ビットと 32 ビットの Windows プラットフォームのリモート オートメーション (RA) を実装します。  
  
 リモート オートメーションは、特定の言語に関連付けられていないが、Visual Basic 4.0 でのみまで Visual C++ 4.2 の Enterprise Edition のリリースで出荷します。 リモート オートメーションが完全 DCOM が含まれていることに注意してください。 リモート オートメーションではなく、アプリケーションで DCOM を使用する機会があれば、これを行う必要があります。 ただしは、リモート オートメーションの方が適しているシナリオがあります。  
  
-   16 ビットのクライアントがあります。  
  
-   場合は、組織は、まだ、DCOM が有効なバージョンの Windows NT または Windows 95 out はロールバックされません。  
  
-   既存のアプリケーション スイートをアップグレードする場合は、1 つまたは複数の Visual Basic コンポーネントの代わりに使用する C++ コンポーネントにリモート オートメーションを使用する必要があります。  
  
 リモート オートメーションと、DCOM 経由でオートメーションを使用して作成されたものを使用するため作成プログラム間で違いことが必要ありませんし、構成ユーティリティを使用するリモート オートメーションおよび DCOM 間の操作を切り替えるには非常に簡単です。 その結果、インフラストラクチャが配置後に DCOM をリモート オートメーションからアプリケーションをアップグレードするが困難ではありません。  
  
## <a name="see-also"></a>関連項目  
 [どのようなリモート オートメーションを管轄します。](what-does-remote-automation-provide-q.md)   
 [DCOM の歴史](../mfc/history-of-dcom.md)
