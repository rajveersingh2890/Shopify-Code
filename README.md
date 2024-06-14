<!DOCTYPE html>
<html>
<head>
	<meta charset="utf-8">
	<meta name="viewport" content="width=device-width, initial-scale=1">
	<title></title>
</head>
<body>

<!-- Adds URL name as add class to body on all pages -->
<script>
	var currentPageUrl = window.location.href;
	var pageName = currentPageUrl.split('/').pop().replace(/\?.*/, ''); 
	if (pageName) {
	    document.body.classList.add(pageName);
	}
</script> 

<script>
    document.addEventListener("DOMContentLoaded", function() {
        var currentPageUrl = window.location.href;
        var baseUrl = 'https://ikshaofficial.myshopify.com/';
        var pageName = currentPageUrl.split('/').pop().replace(/\?.*/, ''); 
        
        if (currentPageUrl === baseUrl || currentPageUrl === baseUrl + 'index.html' || pageName === '') {
        pageName = 'homeindex';
        }
        
        document.body.classList.add(pageName);
    });
</script>
<!-- Adds URL name as add class to body on all pages -->


// JavaScript code for redirecting from a subpage to the home page
<script>     
if (window.location.href != "https://www.google.com/") {
 window.location.href = "https://www.google.com/";
}
</script>
// JavaScript code for redirecting from a subpage to the home page 



<script>
	const currentUrl = window.location.href;
	const collectionPattern = /\/collections\/([^/]+)\/products\/([^/]+)/;
	const match = currentUrl.match(collectionPattern);
	
	if (match) {
		const collectionName = match[1];
		const productName = match[2];
		const newUrl = `https://geroojaipur.com/products/${productName}`;
		window.location.href = newUrl;
	}
</script>



<script>
    const currentUrl = window.location.href;
    const collectionPattern = /\/collections\/([^/]+)\/products\/([^/]+)/;
    const match = currentUrl.match(collectionPattern);

    if (match) {
        const collectionName = match[1];
        const productName = match[2];
        if (collectionName === "buy-1-get-1") {
            document.querySelector('.template-product .product-info .product-info__block-item[data-block-type=liquid] .buy-get-size').style.display = "block";
        } else  {
            document.querySelector('.template-product .product-info .product-info__block-item[data-block-type=liquid] .buy-get-size').style.display = "none";
        }
    }
</script>

<script>
    const currentUrl = window.location.href;
    const collectionPattern = /\/collections\/([^/]+)\/products\/([^/]+)/;
    const match = currentUrl.match(collectionPattern);

    if (match) {
        const collectionName = match[1];
        const productName = match[2];
        if (collectionName === "buy-1-get-1" || collectionName === "sale") { 
            const buyGetSizeElement = document.querySelector('.template-product .product-info .product-info__block-item[data-block-type=liquid] .buy-get-size');
            if (buyGetSizeElement) { 
                buyGetSizeElement.style.display = "block";
            }
        } else  {
            const buyGetSizeElement = document.querySelector('.template-product .product-info .product-info__block-item[data-block-type=liquid] .buy-get-size');
            if (buyGetSizeElement) { 
                buyGetSizeElement.style.display = "none";
            }
        }
    }
</script>




<!-- https://tdf-jewellery.myshopify.com/   products page js code -->
<script>
    if (document.body.classList.contains('template-product')) {
        var variation = document.querySelectorAll('.metal_color');
        for (let j = 0; j < variation.length; j++) {
            variation[j].addEventListener('click', function () {
                var variantimg = variation[j].querySelector('img').getAttribute('src');
                var productmainimg = document.querySelector('.product__main-photos .product-main-slide.is-selected img');
                productmainimg.setAttribute('src', variantimg);
            });
        }
    }
</script>

<script>
    setTimeout(function() {
      var radioButtons = document.querySelectorAll('input[name="properties[Metal Color]"]');
      var displayParagraph1 = document.querySelector('.metalcolordetails');
      var displayParagraph2 = document.querySelector('.jbdzfkjhcxass');
  
      function updateParagraph(event) {
        event.stopPropagation();
        var selectedRadio = document.querySelector('input[name="properties[Metal Color]"]:checked');
        if (selectedRadio) {
          displayParagraph1.textContent = selectedRadio.value;
          displayParagraph2.textContent = selectedRadio.value;
        }
      }
  
      radioButtons.forEach(function(radioButton) {
        radioButton.addEventListener('change', updateParagraph);
      });
  
      updateParagraph();
    }, 2000);
  </script>
<!-- https://tdf-jewellery.myshopify.com/   products page js code -->








<!-- Loading More Loading... Next Pages -->
<div id="AjaxinateContainer"></div>
<div id="AjaxinatePagination">
    {% if paginate.next %}
        <a href="{{ paginate.next.url }}" id="loadNextPage">Loading...</a>
    {% endif %}
</div>

<script>
    document.addEventListener('DOMContentLoaded', function() {
        const loadNextPageLink = document.getElementById('loadNextPage');
        const container = document.getElementById('AjaxinateContainer');

        if (loadNextPageLink) {
            const options = {
                root: null,
                rootMargin: '0px',
                threshold: 1.0
            };

            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        const url = loadNextPageLink.getAttribute('href');

                        fetch(url)
                            .then(response => response.text())
                            .then(html => {

                                const parser = new DOMParser();
                                const doc = parser.parseFromString(html, 'text/html');

                                const newItems = doc.querySelectorAll('#AjaxinateContainer > *');
                                const newPaginationLink = doc.querySelector('#loadNextPage');

                                newItems.forEach(item => container.appendChild(item));

                                if (newPaginationLink) {
                                    loadNextPageLink.href = newPaginationLink.href;
                                } else {
                                    observer.unobserve(loadNextPageLink);
                                    loadNextPageLink.parentElement.removeChild(loadNextPageLink);
                                }
                            })
                            .catch(error => console.error('Error loading next page:', error));
                    }
                });
            }, options);

            observer.observe(loadNextPageLink);
        }
    });
</script>
<!-- Loading More Loading... Next Pages -->








{% for variant in product.variants %}
{% if product.selected_or_first_available_variant.id == variant.id %}
{{ variant.metafields.custom.dimensions_variants }}
{% endif %}
{% endfor %}
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script type="text/javascript">
jQuery(document).ready(function($){
$(".no-js-hidden").on("click", function(){
var refreshint = setInterval(function(){
location.reload();
}, 1000);    });   });
</script>



















<!-- mouse hover par zoom css code js code -->
<style>
.col-sm-10.gutter .slick-initialized .slick-list .slick-track .slick-slide {
    position: relative;
    overflow: hidden;
}
.col-sm-10.gutter .slick-initialized .slick-list .slick-track .slick-slide img.engoj_img_main {
    width: 100%;
    height: 100%;
    transition: transform 0.3s ease;
}
.col-sm-10.gutter .slick-initialized .slick-list .slick-track .slick-slide:hover img.engoj_img_main {
    transform: scale(2); 
}
.col-sm-10.gutter .slick-initialized .slick-list .slick-track .slick-slide {
    cursor: crosshair;
}

</style>
<script>
$(document).ready(function() {
    const zoomScale = 2; // Set the desired zoom scale here

    $(".slick-slide")
        .on("mouseover", function() {
            $(this)
                .children(".engoj_img_main")
                .css({ transform: "scale(" + zoomScale + ")" });
        })
        .on("mouseout", function() {
            $(this)
                .children(".engoj_img_main")
                .css({ transform: "scale(1)" });
        })
        .on("mousemove", function(e) {
            $(this)
                .children(".engoj_img_main")
                .css({
                    "transform-origin":
                        ((e.pageX - $(this).offset().left) / $(this).width()) * 100 +
                        "% " +
                        ((e.pageY - $(this).offset().top) / $(this).height()) * 100 +
                        "%"
                });
        });
});

</script>


<style>
.col-sm-10.gutter .slick-initialized .slick-list .slick-track .slick-slide {
    position: relative;
    overflow: hidden;
    cursor: crosshair;
}
.col-sm-10.gutter .slick-initialized .slick-list .slick-track .slick-slide img.engoj_img_main {
    width: 100%;
    height: 100%;
    transition: transform 0.3s ease, transform-origin 0.3s ease;
}
.col-sm-10.gutter .slick-initialized .slick-list .slick-track .slick-slide:hover img.engoj_img_main {
    transform: scale(2);
}

</style>

<script>

$(document).ready(function() {
    const zoomScale = 2; // Set the desired zoom scale here

    $(".slick-slide")
        .on("mouseover", function() {
            $(this)
                .children(".engoj_img_main")
                .css({ transform: "scale(" + zoomScale + ")" });
        })
        .on("mouseout", function() {
            $(this)
                .children(".engoj_img_main")
                .css({ transform: "scale(1)" });
        })
        .on("mousemove", function(e) {
            const $img = $(this).children(".engoj_img_main");
            const offsetX = (e.pageX - $(this).offset().left) / $(this).width();
            const offsetY = (e.pageY - $(this).offset().top) / $(this).height();
            $img.css({
                "transform-origin": (offsetX * 100) + "% " + (offsetY * 100) + "%"
            });
        });
});
</script>

<!-- mouse hover par zoom css code js code -->


</body>
</html>
