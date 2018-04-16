---
title: "分離アプリケーションの C と C++ のビルド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 76b0c1fa5b509ae495a12fb63164d7da01f402aa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="building-cc-isolated-applications"></a>C/C++ 分離アプリケーションのビルド
分離アプリケーションでは、サイド バイ サイド アセンブリにのみ依存し、その依存関係が、マニフェストを使用してバインドします。 Windows 上で動作するために完全に分離するアプリケーションの必要はありません。ただし、アプリケーションを完全に分離に投資すること、可能性があります時間を節約してアプリケーションに将来のサービスを提供する必要がある場合。 アプリケーションを完全に分離の利点の詳細については、次を参照してください。[分離アプリケーション](http://msdn.microsoft.com/library/aa375190)です。  
  
 Visual C を使用してネイティブ C/C++ アプリケーションをビルドするときに既定では、Visual Studio プロジェクト システム マニフェスト ファイルを生成 Visual C ライブラリへのアプリケーションの依存関係について説明します。 これらは、唯一の依存関係、アプリケーションに場合、Visual Studio で、再構築は、独立したアプリケーションになります。 アプリケーションが実行時に、その他のライブラリを使用するかどうかに記載の手順に従って、サイド バイ サイド アセンブリとしてこれらのライブラリをリビルドする必要があります[C/C++ サイド バイ サイド アセンブリを構築する](../build/building-c-cpp-side-by-side-assemblies.md)です。  
  
## <a name="see-also"></a>参照  
 [分離アプリケーションとサイド バイ サイド アセンブリの概念](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C/C++ 分離アプリケーションおよび side-by-side アセンブリのビルド](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)