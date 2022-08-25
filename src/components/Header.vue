<template>
  <nav class="navbar" role="navigation" aria-label="main navigation">
    <div class="navbar-brand">
      <a class="navbar-item" href="https://bulma.io">
        <img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAjYAAABZCAMAAAAaVZ6hAAAAkFBMVEX///8bGxoAAAAYGBfKysq8vLwXFxYUFBMqKikODgzx8fHh4eH6+vpnZ2bHx8dEREOXl5bU1NNvb2/o6OdDQ0L19fWDg4La2tqwsK+fn58lJSPr6+tbW1rR0dHe3t54eHdTU1IyMjFLS0qQkJA5OTiBgYB3d3a2trZra2pfX19XV1alpaU1NTSTk5MgIB4tLSx4APBeAAAUDklEQVR4nO2d6YKquhKFSVBiEHBEFGdxptX3f7ubSgIyJA50nz6e26w/u7dGDPBZqaQqhWFUUzxN/3TGXb/iUWr9/8tuOunfESVt+acTUxzZ/06Xan287BHeSaviXK4WMQU3fkwtE19qbmqpxKi5kh2nw+mGBCFyBW6AGoRqbmopxajZXDZ0xOjwuy1iXQki60BQQwhwM31+kFp/TECNZzQYN1NOTTiaMW6Gc6DGWp2RWXNTqyRBjWF4KzqKboSEkRGcMLLCq4nIqtFzgZvaL66V02CEOx7/qzGjxCLhhfnGwYkyWJitYe/0XLPmplZegx0eNsSf0yVj5SbWaeYYIWRxK2QEjBuERzU3tRIxajqSGru7tkwyDOBvZ0Lu2CTc1Ot+tYTaO5pQA94wuYVoN4VZOGUjFBWDFNPCtWpuaiUCaubiT//CqGlNmme6tI0LYtRsj5i5xJKbE5uH0109TtVi1CzJRlLjRCGbQzG/prGiy13I5lDDXuDeuWnPmN9DljU3tdpLmlIzulrM1sAoNF8hZmvoesF8GrA30r8ZrBg3qObmzytDjbFDbOY94dFMp28xZzjkQSnOjXR+7E3NTS1jsMQpNUtishGK/8lGKxMhLEPgCxintqKZPwRu9jU3f1lZavrUtK4JNeANY3qWby3A3twkN9vav/njmu4z1GBkoQv/04kI82tC74pX8s02cHNN7A1m86mamz+rQR+vstRIW+NHGLzhgTFg3Mi8rTazRQRLbphfjPC+jmv+TQ32+JxQs6d3ai6MGtIBv6bdwjO5utfuk5Qbe8asEV4Ofr/Ltf51ATVybdhh3nBCjd0FajYL/p/FFrtyNGr3TdOS3ExPwM2u5ubviY1QsySisGNOboYak5wD2Sro4KMcjdp9ZFpUfGTA41M1N4Zjc31iwMXxedec5y2hseP7/gtNM9TYfL0mS80sSNsFK9yXdAhu5vLjCLhpGxU1nTcaDe+RW21Di0a5RbuhVa98FH3jRo75hac/qo4JZ7Dw4mjZPy5HsRcM9Oj488Ih50HQLjV3ei+fGL8GD33L6WJ+iEb7/e5J10B2O2gc4m43HjeC9uOZToaaqVgbFkcAaqxTtpvBDPclHTBOESTjDP2r9Q1uDjfMNNI3cGJogBulN7pYq1X5MFTb+Bpn2y0fHFVBI5MfxG7I3qZM7B80m8x1l3z+Vf72cvPpStuFc+GAEXzvQfNt7Nq1m8stFn170jVGwjzapFeJbEbNhd7oDI74JL1hTs1NXEP7UqIGkrXwPuWG+cUtyc3yO9w0hxZi07EyFYl6Q0jaoAps2DROLXoqH6ZlaRpbX+Nsux3WHzUoH9Zwgu4QU/PezKT4Nmqof9a9DikelTVH0TzXajrTnZlVPLGuicxWU3fppuMTxST3XbfRXN0131teMUnPg8168DnW3dM2o0ayMchSEwE1bvHX1WPcLOQH2YyLfIkOC26W1bgR2NCNznzaI34fPxUbe3ym/MZYBKwN4d9i4e1EeTUENmZG/Bbhbe7OM2xy798/QN7BxpnvrlQgwPpGiGXyrg0nKkfUjr8E+6wxEWeBKO57yiMv2AglrwVQQ9cxt0vsVqmogYTQlBs2/UJkm+Omkl8ssEF4on7bOfCz/VRsBlGL8ptB1yv3eHRXW/HzJqQ/LzWW2FzDuxDmzWmY7YN9QmmDK8p+4HosXgM9Nk7zzGbCYGHC4cx1Z5vhlVtFgpbl8/AnN95tjFvDzWa4JsKA4u1YceTgmKEmZNSMOTX+SDFCyfN2cT/LzVCMq4KbfhVuJDbWVTUCsCNvBByfiU17Dz9MZlx2Y28eLBbB3BtHHTA/ZuoxZgXYkLPXvOtwWcHmM7LO3Hunkb49XsEH4vT/xWPqsXGaHbg+1DpNml4vWPQaXnNybDGSTFo2CM0t4ZSMDk2vMW+wbp1N/vEwLh2ZUXOWDEy5rZHU7GAOpRzItdwMljCfOlbgRmKDqKtywJxI3kU9Ni+6xAIbomgc6lxi0bH7R0ou8XQPv0l6i7zMZMaeT4bQaZUHDdjQfe4lvzfhGxhXyms3PVJE+/rhX4+NB9SYdDYO7tcVPGRmbRCeFbrWPvLG0X1S5gfjFbdNZtHegK1JqNkxar7u1CCSvFNS4OKjPI3BMsPNnnPzfpwhwcZEZa7ZySPzCTb40ixL8UPn2JDOWNE6d1d66cuXLf/I6pAetTAL8UdwYfGpWXy90QffEs9KV4Nj0y+86DdDC5nXSHV1Bm5FbCAfClloFBR+jNN4y46ICiPouAVGKM6dhxPA0gq1Cu4Nu/8JG/YyY2uW7JTJWd9TNp9y5S8jy820z5wQ6r5tbxJskNUpk8qDXk+wUXttJXFsaPlO6uVtuNtx1E1DnTEwTfcKszwYwVt4WXxdiY1hHJh1IhvVJa+KjQNjrRV2y9Nt59BhHnh+AuKDTcelWiLTPboHuKUYNSd5n/wlylDDvHeqtpjJJ0/4lHCzA79YcGPDT+x9blJskLkvvXlJHY0PxGYK/oDmnto7E36/xRuqwcZgM27rprK2VbFpMDtookg1PXXGbvGSBS58f/lXOz0Vp8dZavqmmY5QMNbQzuOLu5jhs2yR5caHAZKc3uTmjo21Lg6j7fs6wudh48DKAJ2pJkyGcErYlSm8qsOmwQ5llmyTUR0bsNK6lBanFGZosDOlrqL1tPAaUCM747jEJPKOCWq2zzJo2iu8kW04N3Ia4JzA2J7eW7+5Y8McqgJym/tc6fOwmcImoLXKRHDBrUC4sICrw8aABBVX8XpFbGA3JF3pl1AL8tg9eCVvCsaZpC8zapJbQg34J63ngazBBm9lK+7fhLLnM/y2vclgY6J8jCHOzIU/DxvwB+hSf60i2DNfMDdabNh4R2eKIaUiNmDqkNLHVopj8/zSLDLUbCDLM6GGQlbWK5HS6RAndE1H2CTJKH6Ga/mWvclgw9zr7BXws0v2n4cNm/5YW304iJlkck/CltJiA6+fFX2riA3MhTURNJWEZdQMt6mCGXaz1MgRyt6DqRy+Fl+3O/gmfx02m4daWFZtc9m9Tr2mV5TFht2jjKWUkZnrZ2ITwA+k/+hijaB3efupxYZZJtUaZUVsmmD0dw+6VhC4xIh8PR4lGDVHeV8dZh2IXCWdstHGJKtXM4NtNk7JttOReefmCHlb7uvcCGyIKwIiMtcHJKIK1mZEPxIbNkaZYVf5VvL5rcXsZ+4lHTZTuM8qnKphAzUf9F5XWXwCjujXg5A3p0YuNfgnmlIDvq1JTq/nkzNuNpJPWGNOuHH2kLflqteYFZIR8PFe0JH6cTZf7jZb3ebjUOab2LyRL/8YG/amNdTGnkE+a2KS3Kd12HAGL4pjVMOGXTqyeX2MYjfhS0SkYm0uF/OGE2psmEMl1Ijo5TurvNMVXskTAm5MyQ2sAqH0O573WGAT+y0eSE43lu/EpNy1x0+waYrctYyUwXSxSnxuFxvrk94eYwPuw/mxWXch2JTrtwabtgW7pVW+RTVsuIP5Tp6hH/HVeBNvx+pMLsi1SqKXbDyh65QaZJpvxpQGs0xMK2T2Rq777a5vcCOxmRhjToEl3XNvzUujbD3jCTbUHRW066puNMfG/FoWW4+0FuMhNj4MK8V4dEF8LpUbK9TYDMB5NlVjVDVsbFghLq+dPlLQRzJmt47mg9IZZ6mBVb51xtagB91Ta+CmEXRhbw7p3yj9nidKsYGdNiiJM9snImfkzhNsEC3l7W212EAaQUGWdp76EJse9OqJ1wmRnvzhVdjY8zOBOLxylaUSNqxvmhCXXr39VeRzWZie4l5+1OnN0vg15ANTOYHktgbt36WGZ5Se7tyYFk24Ccmr9uaOzWIthimo+tZtCX94+hybkohyMqhJnDDDatg0X7g1zZtZ+NVzbE6L4K65F90g+myqPJuK2DSfeusKtScbkW8GP62vUTMTA+2d6VJSs9gzd60js2Ug5h1Wys5r72mSlzONQtNCIkYxjW4QD3/FK7tjI5f3IPdrzu+YaR2MT8Xm8MKtma8tZOUGMsDGXM/OqVYdhHmt553aFamEDfTtpkl7eyDvsqLUkiYHzeJecuIjfEu+Ir6mmR9Ok1FjfT2cFei/y6IXefjeFywWCvPG7zuevOCWZbCx5TDVny/F8APm/EOxYb0yW09uTU+JjUi7TAVWleBI41VWwgb6pgyMPpEzH++2Mi/apHQWy04Vrc3w+9amr7Y2oyrWxpjfuN96nfFMFwtBj55iY5GC1CuWEptSa/1I821r0wBscp6MIgUdkr07se73VdnaPENao6kXH0NJDr3u5eQu4xH/iG8DGexq3+bluVQWG38iolAi8I35D+YZNta2MyxImScosAmHxdYb7c/yITYe+DYPtunwUwPfJhfX5thYBZ98NdEv61f3bdS+0gtaeJMZHznZ0HmWh/7xmdTp52ZSTO1TJuYtNjM8wwbHQVHKJWqxbrPySq21S1UPsVlUnklZnSij7rixeDCUV8IG4h7PkH4kf+FFa0hfR3QoF1N/bd3mRWry2BhemLogMrT2FJt/Z5XYeXHdxsrlEPGZ1DG7Pvlk32wlbHxdqOJ12b0R3yxDh/K7H64Sv5XzUFgltr61Siyx8btJskQSBPxhbH4sJmVCkPmxeXYt5rjkroM2lKlTtVViSGRQpWG8I7/Js53SAGuGm3JM6o3LqotJ9SEm9TI1BWzAaxfuzU325FOxYf20ts9jUmbupV/CZgMxqWd5EE/V4ykIaT4F5E1oIuDojQh45ycj4PfddQexExEn1+JTsZk8Xe/jEfBV7qVfwgYio+9EwDVqgL2hqQP3ON/mNeNWzrcR/6mYb3PHRmzevSfefCo2A1xIDyoJgrE4P0f/JWwgJ5SoUpPfVDdkztk99eNns/uW2CTkm9l9mb28kGpmWekhPhUbyE4oJ81n1OYrnnmufgkbA/YsfX+UMgI4hTDz/38ol/hcNZc4uwU8RhaO0z58LDYxT+/TmxuYR9FN/rXfwobvknozmKmQz72bzAuZnQvgjfzozoX3ZvFlbBiImS0MH4uNf2UTpVC7GCvycwud+y1s2ny/3otXBqQ5R1hGa2VfKO6TWv+7+6RyBSea2RP+WGyMLt9Vovl6Gy5G0dj8GjZ86wLVlHD1p8UzcrxYeddgkLLy5/BzuzKHP7ArM4eN08uYu8/FxobN+VSd/mrDbl6TFN2LX8MmQMwUmupdmZNOM39K/niLFdt+RfoKLSyF/yN7wN+vHaDAJqfPxcaALf/s/Xm5ARQLYl0reRe/ho1zoZo94H78hcNx9nV7ElITX8q/d081zpYqTqxfqjjR+0cqTnwDG1XFCcWFfFBxQrM0+RQbpwubK/DqUKw4Md9bQE15e+yvYWPYrrriRLt7I4jkWAhgImPifaHupt2EHcGFrRe8fcX6Ngk1+xI1levbVMdGWd+Glo+jr29TNgpCT7Ex7B3E6mk48jInbs8nHVHApPzL+z1sjB6Hgc7GmV0szqJ5pGz0osds1xyP1/XA64uXRlWdthetec0b1QjYx0nd4UGWG10NtnxVpH6xmta+ejWtb2CjkBWWj6OtppXdm5XTc2yYb4d45az1ctwsVNNSlKz6VWyMxpmvmyI3bjaCdnvRazQnLsQnLbLPA+14J1EULHS7h2bTazYPk/6a8qxD5U+q3U8LK4kqbLJ2X0R/uXbffxQbY3pZ89p9FK83J167j4jafaaiQN7vYuM0XH7nKW5tTv3+cdYRtftoa1Q6Xm/J492QoH9df61Dinl2KKGa5y+/Xyk0qTD7s5VC/6vYGPbhpKoU2lGW4/xVbAxjEbV41ozJu0ZF/ildjRUoDOI0Ad2yRJFNOItYt4JXqkucrWbtPq5LfJN1ifc/UJf4v4oN8xcmHUwzB4fE/0hT/Pd3sWFebd8s1CXeXnrK8/F7lyGm97YWnEXjQT3rl6ugMyfrTg1zmq9JFfRvVc8XVdCxNi2XYcP1VhV0hUusr4KudYl5/XB8ehZr8YPxsYXTKujXU9zT/Uh5FfQnyV05DWbsAw/yCZ5UQTcG3miIcVIF/VHXDDs4LIfpNdkex/qm/MiZZy6MCs9csB48c0EmYgyOP/DMhYan94sG4iEIbz1zQbFV7UFjTd/Fsx4aL2QOOYNF4+VnLngvpyLBkQPogf6Az5+5YLd7hws8cyGKG4vHz1xwpu3AG0+6k3GztyhvzSyIObf3J7yYrz7hJaGmfsKL0FuPUfldia698tgW3vilB7wYlZ4nRernSdVi3KzuT68z80+vG6qeXkfrp9fVqp+VWauS3nsybygmWPxJ4PWTef+y3nkO+Lp+DngtqSw3SyudhztRaN4LXi5cnJZ94tSgfU3N31Z7SVNuxPqN3PcEUa6QcxOAremISZe9AWpqW/PnleUmuhLGDcyd5iuoakXXgaRGJmzCE0RqamoZwE26S4KNTYKbxooudyFUSu0FMELJ3Nn2jFFj1dTUMqDQDe1IbvxLi5DWpLmCmdIFQcXv452axYmwOdSupqYWCLhJ4gycmxDtppD9CI+loMhKqbFMhEef+Kj0Wv+GBjs8TOKa3bVlkqGISU14uVfp1wQ8DlVTUytVhpsp1GC/iWeawa7iBBugxsSavK9af1ODEe5wOpzGjBI2D4d6r8GJEWSKQarnsj9xVFNTKyt7hLlV8VY0utzYfCqCtD5khVDTe9XocVtTU1OrIOCmCcVNRrbfbRErHM0IrA3HlM2nVmewNZc6elmrKHuHN5cNz1rn3EAJ43Vg+MANYTPvmppaKjF7cyXC53W6/OHmVwgucG4YNcr9wrVqMW6Sau7O5WoRJEKZwA2zNTU1tdSyM0UJIkqS9D0nprU3XOs1xXdXxhm/8hyFWv9P+h+hTdZ/gIJ8pAAAAABJRU5ErkJggg==" width="112" height="28">
        <!-- <img src="data:image/png;base64,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" width="112" height="28"> -->
      </a>

      <a role="button" class="navbar-burger" aria-label="menu" aria-expanded="false" data-target="navbarBasicExample">
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
        <span aria-hidden="true"></span>
      </a>
    </div>

    <div id="navbarBasicExample" class="navbar-menu">
      <div class="navbar-start">
        <a class="navbar-item">
          About
        </a>

        <a class="navbar-item">
          Contact
        </a>

        <a class="navbar-item">
          Costum Suppliers
        </a>

        <div class="navbar-item has-dropdown is-hoverable">
          <a class="navbar-link">
            Products
          </a>

          <div class="navbar-dropdown">
            <a class="navbar-item">
              Lenses
            </a>
            <a class="navbar-item">
              Mirrors
            </a>
            <a class="navbar-item">
              Optical Filters
            </a>
            <hr class="navbar-divider">
            <a class="navbar-item">
              Optomechanics
            </a>
          </div>
        </div>
        <div class="navbar-item has-dropdown is-hoverable">
          <a class="navbar-link">
            Services
          </a>

          <div class="navbar-dropdown">
            <a class="navbar-item">
              System Integrations and Assemblies
            </a>
            <a class="navbar-item">
              System Integrations and Assemblies
            </a>
            <a class="navbar-item">
              Custom Optics
            </a>
          </div>
        </div>
      </div>

      
      
      <div class="navbar-end">
        <div class="navbar-item">
          <div class="buttons">
            <a class="button is-danger">
              <strong>Shop</strong>
            </a>
            <a class="button is-light">
              Log in
            </a>
          </div>
        </div>
      </div>
    </div>
  </nav>
</template>