# projeto-reactjs-com-typescript-e-vite

Aqui está um passo a passo para criar um projeto ReactJS com TypeScript e Vite que exemplifica o uso do Material-UI (agora conhecido como MUI).
Passo 1: Criar um novo projeto com Vite
Primeiro, crie um novo projeto React com TypeScript usando Vite.
bash
Copiar código
npm create vite@latest react-mui-example --template react-ts
cd react-mui-example
npm install
Passo 2: Instalar o Material-UI (MUI)
Instale o Material-UI (MUI) e seus pacotes essenciais.
bash
Copiar código
npm install @mui/material @emotion/react @emotion/styled
npm install @mui/icons-material
Passo 3: Estrutura básica do projeto
No seu projeto, organize as pastas e arquivos da seguinte forma:
css
Copiar código
src/
│
├── components/
│   ├── Header.tsx
│   ├── ButtonComponent.tsx
│   └── CardComponent.tsx
│
└── App.tsx
Passo 4: Implementando o componente Header usando MUI AppBar
Header.tsx
typescript
Copiar código
import React from 'react';
import AppBar from '@mui/material/AppBar';
import Toolbar from '@mui/material/Toolbar';
import Typography from '@mui/material/Typography';

function Header() {
  return (
    <AppBar position="static">
      <Toolbar>
        <Typography variant="h6">
          React with Material-UI
        </Typography>
      </Toolbar>
    </AppBar>
  );
}

export default Header;
Passo 5: Implementando o componente ButtonComponent usando MUI Button
ButtonComponent.tsx
typescript
Copiar código
import React from 'react';
import Button from '@mui/material/Button';

interface ButtonComponentProps {
  label: string;
  onClick: () => void;
}

function ButtonComponent({ label, onClick }: ButtonComponentProps) {
  return (
    <Button variant="contained" color="primary" onClick={onClick}>
      {label}
    </Button>
  );
}

export default ButtonComponent;
Passo 6: Implementando o componente CardComponent usando MUI Card
CardComponent.tsx
typescript
Copiar código
import React from 'react';
import Card from '@mui/material/Card';
import CardContent from '@mui/material/CardContent';
import CardActions from '@mui/material/CardActions';
import Typography from '@mui/material/Typography';
import ButtonComponent from './ButtonComponent';

function CardComponent() {
  const handleClick = () => {
    alert('Button inside Card clicked!');
  };

  return (
    <Card sx={{ maxWidth: 345, margin: '20px auto' }}>
      <CardContent>
        <Typography gutterBottom variant="h5" component="div">
          Material-UI Card
        </Typography>
        <Typography variant="body2" color="text.secondary">
          This is a simple card component using Material-UI in a React app.
        </Typography>
      </CardContent>
      <CardActions>
        <ButtonComponent label="Click Me" onClick={handleClick} />
      </CardActions>
    </Card>
  );
}

export default CardComponent;
Passo 7: Atualizar o componente App.tsx
App.tsx
typescript
Copiar código
import React from 'react';
import Header from './components/Header';
import CardComponent from './components/CardComponent';

function App() {
  return (
    <div>
      <Header />
      <CardComponent />
    </div>
  );
}

export default App;
Passo 8: Executar o projeto
Para executar o projeto, use o comando:
bash
Copiar código
npm run dev
Acesse http://localhost:3000 no seu navegador para ver a aplicação funcionando.
Explicação
•	MUI (Material-UI): É uma das bibliotecas de componentes de interface de usuário mais populares para React. Ela oferece uma ampla variedade de componentes pré-construídos que seguem as diretrizes de design do Material Design do Google.
•	AppBar e Toolbar: São usados para criar barras de navegação e cabeçalhos de páginas.
•	Button: É um componente básico que segue as diretrizes de design do Material Design.
•	Card: É um container versátil para exibir conteúdo de forma agrupada.
Este exemplo demonstra como usar componentes básicos do MUI para construir uma interface de usuário com uma barra de navegação, botões e cartões em uma aplicação React.
