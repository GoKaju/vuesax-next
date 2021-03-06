---
PROPS:
  - name: v-model
    type: boolean, Array
    values: boolean, Array
    description: Determina el valor de el componente y si es un array agrega o elimina el valor.
    default: null
    link: null
    usage: '#dafault'
    code: >
          <template>
            <div class="center con-switch">
              <vs-switch v-model="active" />
              <vs-switch v-model="active2" />
              <vs-switch v-model="active3" disabled />
            </div>
          </template>
  - name: val
    type: string
    values: string
    description: Cambia el valor por defecto de boolean al string para usarlo el ser un array el v-model.
    default: null
    link: null
    usage: '#array-value'
    code: >
            <template>
              <div class="center con-switch">
                <vs-switch val="html" v-model="options">
                  Html
                </vs-switch>
                <vs-switch val="css" v-model="options">
                  Css
                </vs-switch>
                <vs-switch val="javascript" v-model="options">
                  Javascript
                </vs-switch>
                <vs-switch val="vue" v-model="options">
                  Vue
                </vs-switch>
                <vs-switch val="vuesax" v-model="options">
                  Vuesax
                </vs-switch>

                <span class="data">
                  {{ options }}
                </span>
              </div>
            </template>

  - name: color
    type: String
    values: Colores principales de vuesax, RGB y HEX
    description: Cambia el color de el componente cuando esta en estado de activo.
    default: primary
    link: null
    usage: '#color'
    code: >
            <template>
              <div class="center con-switch">
                <vs-switch v-model="active1" />
                <vs-switch success v-model="active2" />
                <vs-switch danger v-model="active3" />
                <vs-switch warn v-model="active4" />
                <vs-switch dark v-model="active5" />
                <vs-switch color="#7d33ff" v-model="active6" />
                <vs-switch color="rgb(59,222,200)" v-model="active7" />
              </div>
            </template>

  - name: loading
    type: boolean
    values: true, false
    description: Agrega una animación de cargando al componete.
    default: false
    link: null
    usage: '#loading'
    code: >
            <template>
              <div class="center con-switch">
                <vs-switch v-model="activeLoading">
                  Active Loading
                </vs-switch>
                <vs-switch :loading="activeLoading" v-model="active2" />
              </div>
            </template>
            <script>
            export default {
              data:() => ({
                activeLoading: true,
                active2: false
              }),
            }
            </script>

  - name: indeterminate
    type: boolean
    values: true,false
    description: Determina si el componente se encuentra en un estado de indeterminado (al estar en este estado se encuentra en disabled).
    default: false
    link: null
    usage: '#indeterminate'
    code: >
            <template>
              <div class="center con-switch">
                <vs-switch indeterminate v-model="active" />
                <vs-switch indeterminate v-model="active2" />
                <vs-switch indeterminate v-model="active3" disabled />
              </div>
            </template>

  - name: Square
    type: Boolean
    values: true,false
    description: Cambia el estilo de el componente de circular a cuadrado.
    default: false
    link: null
    usage: '#square'
    code: >
            <template>
              <div class="center con-switch">
                <vs-switch square v-model="active" />
                <vs-switch square v-model="active2" />
                <vs-switch square v-model="active3" disabled />
              </div>
            </template>

  - name: icon
    type: boolean
    values: true,false
    description: Cambia el estilo de el circulo volviéndolo transparente (se usa cuando se agrega el slot="circle").
    default: false
    link: null
    usage: '#icons'
    code: >
            <vs-switch color="#7d33ff" icon v-model="active6">
              <template #circle>
                  <i v-if="active6" class='bx bxl-instagram-alt'></i>
                  <i v-else class='bx bxl-instagram' ></i>
              </template>
            </vs-switch>

  - name: notValue
    type: String
    values: String
    description: Determina el valor de retorno de el componente al estar inactivo.
    default: null
    link: null
    usage: null
    code: null

SLOTS:
  - name: default
    type: slot
    values: null
    description: Agrega un texto dentro de el componente.
    default: null
    link: /api/slot
    usage: '#text'
    code: >
            <template>
              <div class="center con-switch">
                <vs-switch v-model="active">
                  Suscribe
                </vs-switch>
                <vs-switch v-model="active2">
                  <template #off>
                      Off
                  </template>
                  <template #on>
                      On
                  </template>
                </vs-switch>
                <vs-switch v-model="active3">
                  <template #off>
                      default
                  </template>
                  <template #on>
                      Premium
                  </template>
                </vs-switch>
              </div>
            </template>
  - name: on
    type: slot
    values: null
    description: Agrega un texto dentro de el componente cuando esta en estado activo.
    default: null
    link: /api/slot
    usage: '#icons'
    code: >
            <vs-switch v-model="active1">
              <template #off>
                  <i class='bx bxs-volume-mute' ></i>
              </template>
              <template #on>
                  <i class='bx bxs-volume-full' ></i>
              </template>
            </vs-switch>
  - name: off
    type: slot
    values: null
    description: Agrega un texto dentro de el componente cuando esta en estado inactivo.
    default: null
    link: /api/slot
    usage: '#icons'
    code: >
            <vs-switch v-model="active1">
              <template #off>
                  <i class='bx bxs-volume-mute' ></i>
              </template>
              <template #on>
                  <i class='bx bxs-volume-full' ></i>
              </template>
            </vs-switch>
  - name: circle
    type: slot
    values: null
    description: Agrega un icono al circulo dentro de el componente.
    default: null
    link: /api/slot
    usage: '#icons'
    code: >
            <vs-switch color="#7d33ff" icon v-model="active6">
              <template #circle>
                  <i v-if="active6" class='bx bxl-instagram-alt'></i>
                  <i v-else class='bx bxl-instagram' ></i>
              </template>
            </vs-switch>

NEWS:
  - square
  - indeterminate
  - loading
  - array-value
---

# Switch

<card>

## Default

<docs-warn />

Genera un elemento switch fácilmente con hermosas animaciones y funcionalidad

<div slot="example">
  <Switch-default />
</div>

<div slot="template">

  ```html{3,4,5}
    <template>
      <div class="center con-switch">
        <vs-switch v-model="active" />
        <vs-switch v-model="active2" />
        <vs-switch v-model="active3" disabled />
      </div>
    </template>
  ```

</div>

<div slot="script">

  ```html{4,5,6}
    <script>
      export default {
        data:() => ({
          active: false,
          active2: true,
          active3: false,
        }),
      }
    </script>
  ```

</div>

</card>

<card>

## Color

Cambia el color de el componete cuando se encuentra en estado de activo, los valores permitidos son (colores principales de vuesax, RGB, HEX)

<div slot="example">
  <Switch-color />
</div>

<div slot="template">

  ```html{3,4,5,6,7,8,9}
    <template>
      <div class="center con-switch">
        <vs-switch v-model="active1" />
        <vs-switch success v-model="active2" />
        <vs-switch danger v-model="active3" />
        <vs-switch warn v-model="active4" />
        <vs-switch dark v-model="active5" />
        <vs-switch color="#7d33ff" v-model="active6" />
        <vs-switch color="rgb(59,222,200)" v-model="active7" />
      </div>
    </template>
  ```

</div>

<div slot="script">

  ```html
    <script>
      export default {
        data:() => ({
          active1: true,
          active2: true,
          active3: true,
          active4: true,
          active5: true,
          active6: true,
          active7: true,
        }),
      }
    </script>
  ```

</div>

</card>

<card>

## Text

Agrega un texto al switch con el slot default o si necesitas un texto diferente para cada estado de el componente puedes usar los slots `on` o `off`

:::tip Autoajustable
  El componente se ajusta al texto que va a mostrar por el estado en el que se encuentre
:::

<div slot="example">
  <Switch-text />
</div>

<div slot="template">

  ```html{4,7,8,9,10,11,12}
    <template>
      <div class="center con-switch">
        <vs-switch v-model="active">
          Suscribe
        </vs-switch>
        <vs-switch v-model="active2">
          <template #off>
              Off
          </template>
          <template #on>
              On
          </template>
        </vs-switch>
        <vs-switch v-model="active3">
          <template #off>
              default
          </template>
          <template #on>
              Premium
          </template>
        </vs-switch>
      </div>
    </template>
  ```

</div>

<div slot="script">

  ```html
    <script>
      export default {
        data:() => ({
          active: false,
          active2: false,
          active3: false,
        }),
      }
    </script>
  ```

</div>

</card>

<card>

## Icons

Agrega iconos al componente en el slot default o los slots de stados `on` o `off`

<div slot="example">
  <Switch-icons />
</div>

<div slot="template">

  ```html{5,8}
    <template>
      <div class="center con-switch">
        <vs-switch v-model="active1">
          <template #off>
              <i class='bx bxs-volume-mute' ></i>
          </template>
          <template #on>
              <i class='bx bxs-volume-full' ></i>
          </template>
        </vs-switch>
        <vs-switch danger v-model="active2">
          <i class='bx bxs-microphone' ></i>
        </vs-switch>
        <vs-switch success v-model="active3">
          <template #off>
              <i class='bx bx-x' ></i>
          </template>
          <template #on>
              <i class='bx bx-check' ></i>
          </template>
        </vs-switch>
        <vs-switch warn v-model="active4">
          <template #off>
              <i class='bx bxs-plane-alt' ></i>
          </template>
          <template #on>
              Active
          </template>
        </vs-switch>
        <vs-switch dark v-model="active5">
          <template #circle>
              <i v-if="!active5" class='bx bxs-moon' ></i>
              <i v-else class='bx bxs-sun' ></i>
          </template>
        </vs-switch>
        <vs-switch color="#7d33ff" icon v-model="active6">
          <template #circle>
              <i v-if="active6" class='bx bxl-instagram-alt'></i>
              <i v-else class='bx bxl-instagram' ></i>
          </template>
        </vs-switch>
      </div>
    </template>
  ```

</div>

<div slot="script">

  ```html
    <script>
      export default {
        data:() => ({
          active1: false,
          active2: false,
          active3: false,
          active4: false,
          active5: false,
          active6: false,
        }),
      }
    </script>
  ```

</div>

</card>


<card>

## Array Value <Badge text="New"/>

Puedes usar el checkbox para agregar o eliminar un valor de un array, ese valor es la propiedad `val`

<div slot="example">
  <Switch-array />
</div>

<div slot="template">

  ```html{3}
    <template>
      <div class="center con-switch">
        <vs-switch val="html" v-model="options">
          Html
        </vs-switch>
        <vs-switch val="css" v-model="options">
          Css
        </vs-switch>
        <vs-switch val="javascript" v-model="options">
          Javascript
        </vs-switch>
        <vs-switch val="vue" v-model="options">
          Vue
        </vs-switch>
        <vs-switch val="vuesax" v-model="options">
          Vuesax
        </vs-switch>

        <span class="data">
          {{ options }}
        </span>
      </div>
    </template>
  ```

</div>

<div slot="script">

  ```html
    <script>
      export default {
        data:() => ({
          options: [
            'javascript',
            'vue'
          ],
        }),
      }
    </script>
  ```

</div>

</card>

<card>

## Loading <Badge text="New"/>

Agrega una animación de cargando al componente con la propiedad `loading`, la propiedad es un `boolean` por lo que puedes agregarla sin ningún valor.

<div slot="example">
  <Switch-loading />
</div>

<div slot="template">

  ```html{6}
    <template>
      <div class="center con-switch">
        <vs-switch v-model="activeLoading">
          Active Loading
        </vs-switch>
        <vs-switch :loading="activeLoading" v-model="active2" />
      </div>
    </template>
  ```

</div>

<div slot="script">

  ```html
    <script>
      export default {
        data:() => ({
          activeLoading: true,
          active2: false
        }),
      }
    </script>
  ```

</div>

</card>

<card>

## Indeterminate <Badge text="New"/>

Agrega un estado de indeterminado al componete con la propiedad `indeterminate`, la propiedad es un `boolean` por lo que puedes agregarla sin ningún valor.

<div slot="example">
  <Switch-indeterminate />
</div>

<div slot="template">

  ```html{3,4,5}
    <template>
      <div class="center con-switch">
        <vs-switch indeterminate v-model="active" />
        <vs-switch indeterminate v-model="active2" />
        <vs-switch indeterminate v-model="active3" disabled />
      </div>
    </template>
  ```

</div>

<div slot="script">

  ```html
    <script>
      export default {
        data:() => ({
          active: false,
          active2: true,
          active3: false,
        }),
      }
    </script>
  ```

</div>

</card>

<card>

## Square <Badge text="New"/>

Cambia el estilo circular a cuadrado con la propiedad `square`, la propiedad es un `boolean` por lo que puedes agregarla sin ningún valor.

<div slot="example">
  <Switch-square />
</div>

<div slot="template">

  ```html{3,4,5}
    <template>
      <div class="center con-switch">
        <vs-switch square v-model="active" />
        <vs-switch square v-model="active2" />
        <vs-switch square v-model="active3" disabled />
      </div>
    </template>
  ```

</div>

<div slot="script">

  ```html
    <script>
      export default {
        data:() => ({
          active: false,
          active2: true,
          active3: false,
        }),
      }
    </script>
  ```

</div>

</card>

<card>

## Example

Un ejemplo usual al usar el componente switch

<div slot="example">
  <Switch-example />
</div>

<div slot="template">

  ```html
    <template>
      <div class="center con-switch">
        <ul>
          <li>
            <p>
              Email messages
            </p>
            <vs-switch v-model="active1" />
          </li>
          <li>
            <p>
              Change theme
            </p>
            <vs-switch v-model="active2">
              <template #circle>
                  <i v-if="!active2" class='bx bxs-moon' ></i>
                  <i v-else class='bx bxs-sun' ></i>
              </template>
            </vs-switch>
          </li>
          <li>
            <p>
              Desktop notifications
            </p>
            <vs-switch v-model="active3">
              <i class='bx bxs-message' ></i>
            </vs-switch>
          </li>
          <li>
            <p>
              Type of user
            </p>
            <vs-switch v-model="active4">
              <template #on>
                Admin
              </template>
              <template #off>
                Default
              </template>
            </vs-switch>
          </li>
          <li>
            <p>
              Allow to send test data to improve this product
            </p>
            <vs-switch success v-model="active5">
              <template #off>
                  <i class='bx bx-x' ></i>
              </template>
              <template #on>
                  <i class='bx bx-check' ></i>
              </template>
            </vs-switch>
          </li>
        </ul>
      </div>
    </template>
  ```

</div>

<div slot="script">

  ```html
    <script>
      export default {
        data:() => ({
          active1: true,
          active2: false,
          active3: false,
          active4: true,
          active5: true,
        }),
      }
    </script>
  ```

</div>

<div slot="style">

  ```html
    <style lang="stylus" scoped>
    .con-switch
      display flex
      align-items center
      justify-content center
      ul
        width 100%
        padding 0px
        li
          width 100%
          display flex
          align-items center
          justify-content space-between
          padding 0px
          p
            margin 0px
      >>>.vs-switch
        margin 5px
    </style>
  ```

</div>

</card>

<card>

## API

</card>
