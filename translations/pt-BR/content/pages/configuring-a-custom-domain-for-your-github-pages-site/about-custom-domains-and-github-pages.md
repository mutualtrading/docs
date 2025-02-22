---
title: Sobre domínios personalizados e GitHub Pages
intro: 'O {% data variables.product.prodname_pages %} permite o uso de domínios personalizados, ou a alteração da raiz do URL do seu site do padrão, como ''octocat.github.io'', para qualquer domínio que você possua.'
redirect_from:
  - /articles/about-custom-domains-for-github-pages-sites
  - /articles/about-supported-custom-domains
  - /articles/custom-domain-redirects-for-your-github-pages-site
  - /articles/about-custom-domains-and-github-pages
  - /github/working-with-github-pages/about-custom-domains-and-github-pages
product: '{% data reusables.gated-features.pages %}'
versions:
  fpt: '*'
  ghec: '*'
topics:
  - Pages
shortTitle: Domínios personalizados no GitHub Pages
---

## Domínios personalizados compatíveis

O {% data variables.product.prodname_pages %} trabalha com dois tipos de domínio: subdomínios e domínios apex. Para obter uma lista de domínios personalizados não compatíveis, consulte "[Solução de problemas de domínios personalizados e {% data variables.product.prodname_pages %}](/articles/troubleshooting-custom-domains-and-github-pages/#custom-domain-names-that-are-unsupported)".

| Tipo de domínio personalizado compatível | Exemplo            |
| ---------------------------------------- | ------------------ |
| Subdomínio `www`                         | `www.example.com`  |
| Subdomínio personalizado                 | `blog.example.com` |
| Domínio apex                             | `example.com`      |

Você pode definir as duas configurações apex e subdomínio de `www` para o seu site. Para obter mais informações sobre domínios apex, consulte "[Usar um domínio apex para o seu site {% data variables.product.prodname_pages %}](#using-an-apex-domain-for-your-github-pages-site)".

É recomendável sempre usar um subdomínio `www`, mesmo se você também usar um domínio apex. When you create a new site with an apex domain, we automatically attempt to secure the `www` subdomain for use when serving your site's content, but you need to make the DNS changes to use the `www` subdomain. Se você configurar um subdomínio `www`, nós tentaremos proteger automaticamente o domínio apex associado. Para obter mais informações, consulte "[Gerenciar um domínio personalizado para seu site do {% data variables.product.prodname_pages %}](/articles/managing-a-custom-domain-for-your-github-pages-site)".

Depois que você configurar um domínio personalizado para um site de usuário ou organização, o domínio personalizado substituirá a parte `<user>.github.io` ou `<organization>.github.io` da URL para qualquer site de projeto de propriedade da conta que não tenha um domínio personalizado configurado. Por exemplo, se o domínio personalizado para o site de usuário for `www.octocat.com` e você tiver um site de projeto sem domínio personalizado configurado que seja publicado de um repositório chamado `octo-project`, o site do {% data variables.product.prodname_pages %} para esse repositório estará disponível em `www.octocat.com/octo-project`.

## Usar um subdomínio para seu site do {% data variables.product.prodname_pages %}

Um subdomínio é a parte de um URL antes do domínio raiz. Você pode configurar seu subdomínio como `www` ou como uma seção distinta do seu site, como `blog.example.com.`.

Os subdomínios são configurados com um registro `CNAME` por meio do provedor DNS. Para obter mais informações, consulte "[Gerenciar um domínio personalizado para seu site do {% data variables.product.prodname_pages %}](/articles/managing-a-custom-domain-for-your-github-pages-site#configuring-a-subdomain)".

### Subdomínios `www`

Um subdomínio `www` é o tipo de subdomínio usado com mais frequência. Por exemplo, `www.example.com` inclui um subdomínio `www`.

Os subdomínios `www` são o tipo mais estável de domínio personalizado, pois os subdomínios `www` não são afetados pelas alterações nos endereços IP dos servidores do {% data variables.product.product_name %}.

### Subdomínios personalizados

Um subdomínio personalizado é um tipo de subdomínio que não usa a variante padrão `www`. Os subdomínios personalizados são usados mais frequentemente quando você deseja duas seções distintas do site. Por exemplo, você pode criar um site chamado `blog.example.com.` e personalizar essa seção independentemente de `www.example.com`.

## Usar um domínio apex para seu site do {% data variables.product.prodname_pages %}

Um domínio apex é um domínio personalizado que não contém um subdomínio, como `example.com`. Os domínios apex também são conhecidos como domínios base, bare, naked, apex raiz ou apex de zona.

Um domínio apex é configurado com um registro `A`, `ALIAS` ou `ANAME` por meio do provedor DNS. Para obter mais informações, consulte "[Gerenciar um domínio personalizado para seu site do {% data variables.product.prodname_pages %}](/articles/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain)".

{% data reusables.pages.www-and-apex-domain-recommendation %} Para obter mais informações, consulte "[Gerenciar um domínio personalizado para o seu site de {% data variables.product.prodname_pages %}](/github/working-with-github-pages/managing-a-custom-domain-for-your-github-pages-site/#configuring-a-subdomain)".

## Protegendo o domínio personalizado para o seu site do {% data variables.product.prodname_pages %}

{% data reusables.pages.secure-your-domain %} Para obter mais informações, consulte "[Verificando o seu domínio personalizado para {% data variables.product.prodname_pages %}](/pages/configuring-a-custom-domain-for-your-github-pages-site/verifying-your-custom-domain-for-github-pages)" e "[Gerenciando um domínio personalizado para o site do seu {% data variables.product.prodname_pages %}](/articles/managing-a-custom-domain-for-your-github-pages-site)."

Há alguns motivos para que seu site possa ser desabilitado automaticamente.

- Se você fizer downgrade do {% data variables.product.prodname_pro %} para o {% data variables.product.prodname_free_user %}, qualquer site do {% data variables.product.prodname_pages %} que esteja publicado no momento usando repositórios privados em sua conta terão a publicação cancelada. Para obter mais informações, consulte "[Fazer downgrade do plano de cobrança do {% data variables.product.prodname_dotcom %}](/articles/downgrading-your-github-billing-plan)".
- Se você transferir um repositório privado para uma conta pessoal que esteja usando o {% data variables.product.prodname_free_user %}, o repositório perderá o acesso ao recurso {% data variables.product.prodname_pages %} e o site do {% data variables.product.prodname_pages %} atualmente publicado terá a publicação cancelada. Para obter mais informações, consulte "[Transferir um repositório](/articles/transferring-a-repository)".

## Leia mais

- "[Solucionar problemas de domínios personalizados e do {% data variables.product.prodname_pages %}](/articles/troubleshooting-custom-domains-and-github-pages)"
