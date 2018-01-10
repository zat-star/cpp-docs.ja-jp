---
title: "方法: 部分的に信頼されたアプリケーションの作成 (C + + CLI) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- partially trusted applications [C++]
- mixed assemblies [C++], partially trusted applications
- msvcm90[d].dll
- interoperability [C++], partially trusted applications
- interop [C++], partially trusted applications
- /clr compiler option [C++], partially trusted applications
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: dfef7eacfa9da8c55155f6e7ce43dfdb79e67e91
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>方法: CRT ライブラリ DLL との依存関係を削除して部分信頼アプリケーションを作成する
このトピックでは、Visual C を使用する msvcm90.dll との依存関係を削除することで、部分的に信頼された共通言語ランタイム アプリケーションを作成する方法について説明します。  
  
 作成された Visual C アプリケーション**/clr** C ランタイム ライブラリの一部である msvcm90.dll との依存関係になります。 部分信頼環境で使用するアプリケーションを実行する場合に、CLR には、DLL での特定コード アクセス セキュリティ規則が適用されます。 したがって、msvcm90.dll とにはネイティブ コードが含まれています、それにコード アクセス セキュリティ ポリシーを適用できないために、この依存関係を削除する必要があります。  
  
 使用する必要が場合は、アプリケーションは、C ランタイム ライブラリの機能は使用しないで、コードからこのライブラリへの依存関係を削除するには、**とき**リンカー オプションとリンクします。 これらのライブラリが初期化とアプリケーションの初期化解除用のオブジェクト ファイルを含む、例外クラスは、初期化コードによって使用され、例外処理コードを管理します。 これらのライブラリのいずれかでリンクすると、msvcm90.dll との依存関係が削除されます。  
  
> [!NOTE]
>  Ptrust ライブラリを使用するアプリケーションのアセンブリの初期化解除の順序が異なる場合があります。 標準的なアプリケーション、アセンブリは通常、それらが読み込まれるが、これは保証されませんを逆の順序でアンロードします。 部分信頼アプリケーションでは、アセンブリは読み込まれている順序と同じ順序で通常アンロードします。 これには、または保証されません。  
  
### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>部分的に信頼を作成するには、混合 (/clr) アプリケーション  
  
1.  Msvcm90.dll との依存関係を削除するを使用してこのライブラリを含めないようにリンカーに指定する必要があります、**とき**リンカー オプション。 この操作は、Visual Studio 開発環境を使用またはプログラムで、参照する方法について[/NODEFAULTLIB (ライブラリの無視)](../build/reference/nodefaultlib-ignore-libraries.md)です。  
  
2.  リンカー入力依存関係を ptrustm ライブラリを追加できます。 リリース モードでアプリケーションを構築する場合は、ptrustm.lib を使用します。 デバッグ モードでは、ptrustmd.lib を使用します。 この操作は、Visual Studio 開発環境を使用またはプログラムで、参照する方法について[です。ファイルをリンカー入力として lib](../build/reference/dot-lib-files-as-linker-input.md)です。  
  
## <a name="see-also"></a>参照  
 [混在 (ネイティブおよびマネージ) アセンブリ](../dotnet/mixed-native-and-managed-assemblies.md)   
 [混在アセンブリの初期化](../dotnet/initialization-of-mixed-assemblies.md)   
 [混在アセンブリのライブラリのサポート](../dotnet/library-support-for-mixed-assemblies.md)   
 [/link (リンカーに渡すオプション)](../build/reference/link-pass-options-to-linker.md)   
