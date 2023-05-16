# PORTAFOLIO
## Empresa
* GAIA Design: Me encargue del category donde se realizaban las busquedas los usuarios empleando filtros donde los usuarios obtenian la data desde algolia, posterior a eso me encargue igual a "Vende en GAIA"
  - Vende en GAIA 
    - Escritorio 
      -  ![image](https://github.com/emmanueljgd1987/emmanueljgd1987/assets/118326896/e6373569-0360-4b15-ac1d-480185ef2842)
      -  ![image](https://github.com/emmanueljgd1987/emmanueljgd1987/assets/118326896/3b15bbca-5e16-4f1b-8969-6e619226fb32)
      -  ![image](https://github.com/emmanueljgd1987/emmanueljgd1987/assets/118326896/93d2d91b-82c1-4cdc-8859-769c47e32fcc)

    - Mobile
      - ![image](https://github.com/emmanueljgd1987/emmanueljgd1987/assets/118326896/1edcbdba-0bc6-4a0b-8392-73884372008f)
      - ![image](https://github.com/emmanueljgd1987/emmanueljgd1987/assets/118326896/3fb885e1-38fd-4acd-8dd1-42d05ffc685e)
  
    - Tablet  
      - ![image](https://github.com/emmanueljgd1987/emmanueljgd1987/assets/118326896/08b5ec86-80da-4489-867d-0d68fcd492e9)
      - ![image](https://github.com/emmanueljgd1987/emmanueljgd1987/assets/118326896/24882256-16d0-4e83-bfe9-9ef3dcf75815)

  
  - Category
    - Escritorio
      - ![image](https://github.com/emmanueljgd1987/emmanueljgd1987/assets/118326896/be505de8-83c7-4ef4-8eaf-38f96c557838)
      - ![image](https://github.com/emmanueljgd1987/emmanueljgd1987/assets/118326896/6402aaaf-8de1-43f7-8f11-3c5a0b41d523)


    - Mobile
      - ![image](https://github.com/emmanueljgd1987/emmanueljgd1987/assets/118326896/37ac8ffc-8dfb-43de-9911-9877cd7770e3)
      - ![image](https://github.com/emmanueljgd1987/emmanueljgd1987/assets/118326896/b40590b2-8a6c-49cd-b2ba-1a952ef1391e)
      - ![image](https://github.com/emmanueljgd1987/emmanueljgd1987/assets/118326896/74048f80-9d47-4aac-874d-6db5a5e00e5e)

    - Tablet
      - ![image](https://github.com/emmanueljgd1987/emmanueljgd1987/assets/118326896/d6c3784b-8567-4bb2-9e36-921c935776dc)
      - ![image](https://github.com/emmanueljgd1987/emmanueljgd1987/assets/118326896/6110d086-1970-46d8-a470-9eac1a113e1e)
      
      
  - Codigo js y less
    - Javascript
      -    
      `   let grid = `<div class="vivia-hits">`;
            grid += `<div class="vivia-hits-ordered-list">
                ${hits.length ? hits.map((hit, index) =>
                    `
                    <div class="vivia-ordered-list-item">
                        <a href="${hit.url}" ></a>
                        <div class="item-vivia" data-id="${hit.product_id}"
                         ${ hit.hasOwnProperty("variants") ? `data-variant='${JSON.stringify(hit)}'` :  '' }
                        >
                            ${(() => {
                                let isIstock = (hit.stock === 0) && (hit.threshold_behavior != 1);
                                if(isIstock){
                                    return `
                                        <div class="gaia-tag sold-out">
                                            <span class="unavailable">Agotado</span>
                                        </div>
                                    `;
                                }
                                if(hit.promotion){
                                    return  `
                                        <div class="gaia-tag is-promotion">
                                            <span class="tag-promotion">${hit.promotion}</span>
                                        </div>
                                    `;
                                } else {
                                    return  `
                                        <div class="gaia-tag not-promotion">
                                            <span class="tag-promotion hidden">${hit.promotion}</span>
                                        </div>
                                    `;
                                }
                                if(hit.is_new && !isIstock){
                                    return  `
                                        <div class="gaia-tag new">
                                            <span class="tag-new">Nuevo</span>
                                        </div>
                                    `;
                                }
                                if(hit.rating >= 4.5 && !isIstock){
                                    return  `
                                        <div class="gaia-tag top-rated">
                                            <span class="tag-rating">Mejor valorado</span>
                                        </div>
                                    `;
                                }
                                else
                                    return '';
                            })()}
                            <div class="item-container">
                                <div class="item-image" data-id="${hit.product_id}">
                                    <a href="${hit.url}">
                                        <img loading="lazy" class="image-card" src='${hit.image}'>
                                        <img loading="lazy" class="image-card-altern" src='${hit.look_image}'>
                                    </a>
                                    <div class="discount-badge">
                                        ${(() => {
                                            if (true) {
                                                return '<div class="discount-badge-text  discount-badge-yellow">Mejor valorado</div>'
                                            } else {
                                                return '<div class="discount-badge-text discount-badge-red">Oferta flash</div>'
                                            }
                                        })()}
                                    </div>
                                    <div class="item-info">
                                        ${(() => {
                                            if (hit.vendor.is_gaia) {
                                                return `
                                                    <div class="item-gaia-vendor">
                                                        <div class="item-vivia-sold-by">
                                                            <div class="border-gaia-container">
                                                                <div class="sold-by-label-text">Selección</div>
                                                                <div class="svgicon svg-gaia_label_black"></div>
                                                            </div>
                                                        </div>
                                                    </div>
                                                `;
                                            } else {
                                                return '';
                                            }
                                        })()}
                                        ${(() => {
                                            if (hit.hasOwnProperty("variants")) {
                                                function colorVariants (variants) {
                                                    var colores = [];
                                                    let colorsNames = [];
                                                    variants.forEach((element, index) => {
                                                        if (isPromotion === "1"){
                                                            if (element.promotion === catName) {
                                                                if (((element.color.name !== hit.color.name && index) ||
                                                                (element.color.name === hit.color.name && !index)) && 
                                                                !colorsNames.includes(element.color.name)) {
                                                                    colores.push(
                                                                        `<a id="product-${element.product_id}" class="item-product-color color${index}">
                                                                            <span id='${element.product_id}'
                                                                                class="item-vivia-product-color dot ${index === 0 ? 'variant-active' : ''}"
                                                                                data-variant='${JSON.stringify(element)}'
                                                                                style='background-color: ${element.color.color};'>
                                                                            </span>
                                                                        </a>`
                                                                    );
                                                                    colorsNames.push(element.color.name);
                                                                }
                                                            }
                                                        } else {
                                                            if (((element.color.name !== hit.color.name && index) ||
                                                            (element.color.name === hit.color.name && !index)) && 
                                                            !colorsNames.includes(element.color.name)) {
                                                                colores.push(
                                                                    `<a id="product-${element.product_id}" class="item-product-color color${index}">
                                                                        <span id='${element.product_id}'
                                                                            class="item-vivia-product-color dot ${index === 0 ? 'variant-active' : ''}"
                                                                            data-variant='${JSON.stringify(element)}'
                                                                            style='background-color: ${element.color.color};'>
                                                                        </span>
                                                                    </a>`
                                                                );
                                                                colorsNames.push(element.color.name);
                                                            }
                                                        }
                                                    });

                                                    if (colores.length > 4) {
                                                        colores.splice(4, 0, `<a class="item-product-number"><span class="color-number"> + ${(colores.length
                                                             >= 4 ? colores.length - 4 : '')} </span></a>`);
                                                        return colores.slice(0, 5);
                                                    } else if (colores.length > 1) {
                                                        return colores;
                                                    } else {
                                                        return [];
                                                    }
                                                }
                                            }

                                            if (hit.hasOwnProperty("variants")) {
                                                if (colorVariants(hit.variants.color).join('').length > 0) {
                                                    return `
                                                        <div id="${hit.product_code}" class="colors-container">
                                                            ${colorVariants(hit.variants.color).join('')}
                                                        </div>
                                                    `;
                                                } else {
                                                    return ``;
                                                }
                                            } else {
                                                 return ``;
                                            }
                                        })()}
                                        <div class="item-vivia-product-name">
                                            <a class="product-title" href= "${hit.url}" >
                                                ${hit.name}
                                            </a>
                                        </div>
                                        <div class="item-vivia-prices">
                                            <div class="item-vivia-product-price ${hit.price_color}">
                                                ${numberWithCommas(hit.price)}
                                            </div>
                                            <div class="item-vivia-product-price-discount" style='display: ${hit.discount_price};' >
                                                <span class="gaia-product-price-discount-one">${numberWithCommas(hit.price_list)}</span>
                                                <span class="gaia-product-price-discount"> - ${hit.discount_price} % </span>
                                            </div>
                                        </div>
                                        ${(() => {
                                            if (hit.free_shipping) {
                                                return `
                                                    <div class="item-gaia-vendor">
                                                        <div class="tags-container" style='display: ${hit.tagDelivery};'>
                                                            <div class="express-delivery-tag">
                                                                <p class="icon-text-gaia">Envío gratis</p>
                                                            </div>
                                                        </div>
                                                    </div>
                                                `
                                            } else {
                                                return '';
                                            }
                                        })()}
                                        ${(() => {
                                            const starRating = (starNumber) => {
                                                return (hit.rating >= starNumber ? '' : hit.rating > starNumber - 1 ? '-middle' : '-null');
                                            }
                                            if (hit.rating && hit.rating > 0) {
                                                return `<div class="container-rating" style='display: ${hit.rating};'>
                                                            ${[1, 2, 3, 4, 5].map(
                                                                v => v !== 1 ? `<span class="rating-category${starRating(v)}"></span>`: '<span class="rating-category"></span>'
                                                            ).join('')}
                                                            <span class="rating-text">(${hit.rating_quantity})</span>
                                                        </div>`
                                            } else {
                                                return ``;
                                            }
                                        })()}
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                `
                ).join('')
                : `
                    <div class="gaia-hits-product-ordered-list">
                        <p class="gaia-hits-product-ordered-list-text">Lo sentimos <span class="gaia-hits-product-text-emoticon">&#128546;</span>,</p>
                            <p class="gaia-hits-product-ordered-list-text"> no encontramos coincidencias para los filtros que seleccionaste</p>
                            <p class="gaia-hits-product-ordered-list-title" id="reloadFilter">Volver a la vista anterior</p>
                    </div>
                `
            }
        </div>`;
        grid += `</div>`;   
        
        `  

 
    

  

       
   
