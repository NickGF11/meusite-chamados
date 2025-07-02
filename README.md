<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sistema de Chamados Técnicos</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #4e9118;
            --secondary: #3498db;
            --success: #2ecc71;
            --warning: #f39c12;
            --danger: #e74c3c;
            --light: #ecf0f1;
            --dark: #34495e;
        }
        
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background-color: #f5f7fa;
            color: #333;
            line-height: 1.6;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        header {
            background: linear-gradient(135deg, var(--primary), var(--dark));
            color: white;
            padding: 20px 0;
            box-shadow: 0 4px 12px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 100;
        }
        
        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 12px;
            font-size: 1.8rem;
            font-weight: bold;
        }
        
        .logo i {
            color: var(--success);
        }
        
        .user-info {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .user-avatar {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--secondary);
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            color: white;
        }
        
        .nav-menu a {
            color: white;
            text-decoration: none;
            margin-left: 20px;
            padding: 8px 15px;
            border-radius: 30px;
            transition: all 0.3s;
            font-weight: 500;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }
        
        .nav-menu a:hover {
            background-color: rgba(255,255,255,0.15);
        }
        
        .main-content {
            display: grid;
            grid-template-columns: 250px 1fr;
            gap: 20px;
            margin-top: 20px;
        }
        
        .sidebar {
            background-color: white;
            border-radius: 12px;
            padding: 20px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            position: sticky;
            top: 100px;
            height: fit-content;
        }
        
        .sidebar-header {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 20px;
            padding-bottom: 15px;
            border-bottom: 1px solid #eee;
        }
        
        .sidebar-menu {
            list-style: none;
        }
        
        .sidebar-menu li {
            margin-bottom: 10px;
        }
        
        .sidebar-menu a {
            display: flex;
            align-items: center;
            gap: 12px;
            padding: 12px 15px;
            color: var(--dark);
            text-decoration: none;
            border-radius: 8px;
            transition: all 0.3s;
            font-weight: 500;
        }
        
        .sidebar-menu a:hover,
        .sidebar-menu a.active {
            background: linear-gradient(to right, var(--secondary), #4aa5e0);
            color: white;
            transform: translateX(5px);
        }
        
        .sidebar-menu a i {
            width: 20px;
            text-align: center;
        }
        
        .content-area {
            background-color: white;
            border-radius: 12px;
            padding: 30px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            margin-bottom: 30px;
        }
        
        .page-title {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 25px;
            padding-bottom: 20px;
            border-bottom: 1px solid #eee;
        }
        
        .page-title i {
            background-color: var(--secondary);
            color: white;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.4rem;
        }
        
        .form-container {
            max-width: 700px;
            margin: 0 auto;
        }
        
        .form-group {
            margin-bottom: 25px;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 10px;
            font-weight: 600;
            color: var(--dark);
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .form-control {
            width: 100%;
            padding: 14px 18px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 1rem;
            transition: all 0.3s;
            background-color: #fafbfc;
        }
        
        .form-control:focus {
            border-color: var(--secondary);
            outline: none;
            box-shadow: 0 0 0 3px rgba(52, 152, 219, 0.2);
            background-color: white;
        }
        
        .btn {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            padding: 14px 28px;
            background: linear-gradient(to right, var(--success), #34c280);
            color: white;
            border: none;
            border-radius: 8px;
            cursor: pointer;
            font-size: 1.05rem;
            font-weight: 600;
            text-align: center;
            transition: all 0.3s;
            box-shadow: 0 4px 10px rgba(46, 204, 113, 0.3);
        }
        
        .btn-block {
            display: flex;
            width: 100%;
        }
        
        .btn-whatsapp {
            background: linear-gradient(to right, #25D366, #128C7E);
            box-shadow: 0 4px 10px rgba(37, 211, 102, 0.3);
        }
        
        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 15px rgba(46, 204, 113, 0.4);
        }
        
        .btn-whatsapp:hover {
            box-shadow: 0 6px 15px rgba(37, 211, 102, 0.4);
        }
        
        .form-row {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 20px;
        }
        
        .urgency-indicator {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-top: 8px;
            font-size: 0.9rem;
            color: #7f8c8d;
        }
        
        .urgency-low { color: var(--success); }
        .urgency-medium { color: var(--warning); }
        .urgency-high { color: var(--danger); }
        .urgency-critical { color: #9b59b6; font-weight: bold; }
        
        footer {
            text-align: center;
            padding: 25px;
            margin-top: 40px;
            color: #7f8c8d;
            border-top: 1px solid #eee;
            background-color: white;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
        }
        
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            margin: 30px 0;
        }
        
        .stat-card {
            background: linear-gradient(135deg, #f8f9fa, #e9ecef);
            border-radius: 10px;
            padding: 20px;
            text-align: center;
            box-shadow: 0 3px 10px rgba(0,0,0,0.05);
            transition: transform 0.3s;
        }
        
        .stat-card:hover {
            transform: translateY(-5px);
        }
        
        .stat-value {
            font-size: 2.5rem;
            font-weight: 700;
            color: var(--primary);
            margin: 10px 0;
        }
        
        .stat-label {
            color: var(--dark);
            font-weight: 600;
        }
        
        @media (max-width: 768px) {
            .main-content {
                grid-template-columns: 1fr;
            }
            
            .sidebar {
                display: none;
            }
            
            .header-content {
                flex-direction: column;
                gap: 15px;
            }
            
            .nav-menu {
                width: 100%;
                display: flex;
                justify-content: center;
            }
            
            .form-row {
                grid-template-columns: 1fr;
            }
            
            .page-title {
                flex-direction: column;
                text-align: center;
            }
        }
        
        .mobile-menu-btn {
            display: none;
            background: none;
            border: none;
            color: white;
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        @media (max-width: 768px) {
            .mobile-menu-btn {
                display: block;
                position: absolute;
                top: 20px;
                left: 20px;
            }
            
            .nav-menu {
                display: none;
            }
            
            .nav-menu.active {
                display: flex;
                flex-direction: column;
                width: 100%;
                margin-top: 15px;
            }
            
            .nav-menu.active a {
                margin: 5px 0;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-content">
            <button class="mobile-menu-btn">
                <i class="fas fa-bars"></i>
            </button>
            <div class="logo">
                <i class="fas fa-headset"></i>  
                <span>Sistema de Chamados</span>
            </div>
            <nav class="nav-menu" id="navMenu">
                <a href="#"><i class="fas fa-ticket-alt"></i> Chamados</a>
            </nav>
            <div class="user-info">
                <div class="user-avatar">INT</div>
                <span>Intellitech</span>
            </div>
        </div>
    </header>

    <div class="container">
        <div class="main-content">
            <aside class="sidebar">
                <div class="sidebar-header">
                    <i class="fas fa-user-cog"></i>
                    <h3>Menu Técnico</h3>
                </div>
                <ul class="sidebar-menu">
                    <li><a href="#" class="active"><i class="fas fa-plus-circle"></i> Abrir Chamado</a></li>
                    <li><a href="https://docs.google.com/spreadsheets/d/1EaUZ44NXLMI5x3PhshXG4POrACIYHPB5/edit?usp=sharing&ouid=113014592914653074602&rtpof=true&sd=true"><i class="fas fa-chart-bar"></i> Relatórios</a></li>
                </ul>
            </aside>

            <main class="content-area">
                <div class="page-title">
                    <i class="fas fa-plus-circle"></i>
                    <div>
                        <h1>Abrir Novo Chamado Técnico</h1>
                        <p>Preencha o formulário abaixo para registrar um novo chamado</p>
                    </div>
                </div>

                
                <div class="form-container">
                    <form id="chamadoForm">
                        <div class="form-row">
                            <div class="form-group">
                                <label for="nome"><i class="fas fa-user"></i> Nome do Solicitante</label>
                                <input type="text" id="nome" class="form-control" required placeholder="Digite seu nome completo">
                            </div>
                            
                            <div class="form-group">
                                <label for="contato"><i class="fas fa-phone"></i> Contato</label>
                                <input type="tel" id="contato" class="form-control" required placeholder="(00) 00000-0000">
                            </div>
                        </div>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <label for="setor"><i class="fas fa-user-tie"></i> Técnico Responsável</label>
                                <select id="setor" class="form-control" required>
                                    <option value="">Selecione um técnico</option>
                                    <option value="nicolas" data-phone="5519999642609">Nicolas - Assistente Técnico</option>
                                    <option value="emerson" data-phone="5519971694650">Emerson - Assistente Técnico</option>
                                    <option value="guilherme" data-phone="5519994554130">Guilherme - Assistente Técnico</option>
                                    <option value="jonatas" data-phone="5519996186648">Jonatas - Assistente Técnico</option>
                                    <option value="alexandre" data-phone="5519994589329">Alexandre - Assistente Técnico</option>
                                </select>
                            </div>
                            
                            <div class="form-group">
                                <label for="categoria"><i class="fas fa-tag"></i> Categoria do Problema</label>
                                <select id="categoria" class="form-control" required>
                                    <option value="">Selecione uma categoria</option>
                                    <option value="Câmera">Câmera</option>
                                    <option value="Controle de acesso">Controle de acesso</option>
                                    <option value="APR">APR</option>
                                    <option value="Problema de rede">Problema de rede</option>
                                    <option value="Outro">Outro</option>
                                </select>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label for="urgencia"><i class="fas fa-exclamation-triangle"></i> Nível de Urgência</label>
                            <select id="urgencia" class="form-control" required>
                                <option value="Baixa">Baixa - Sem impacto nas operações</option>
                                <option value="Média">Média - Impacto parcial</option>
                                <option value="Alta">Alta - Impacto significativo</option>
                                <option value="Crítica">Crítica - Operações paralisadas</option>
                            </select>
                            <div class="urgency-indicator">
                                <span id="urgencyIcon"><i class="fas fa-info-circle"></i></span>
                                <span id="urgencyText">Selecione o nível de urgência</span>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label for="descricao"><i class="fas fa-file-alt"></i> Descrição Detalhada</label>
                            <textarea id="descricao" class="form-control" rows="6" required placeholder="Descreva detalhadamente o problema, incluindo qualquer mensagem de erro, passos para reproduzir o problema, e o impacto causado..."></textarea>
                        </div>
                        
                        <button type="submit" class="btn btn-whatsapp btn-block">
                            <i class="fab fa-whatsapp"></i> Abrir Chamado via WhatsApp
                        </button>
                    </form>
                </div>
            </main>
        </div>
    </div>

    <footer class="container">
        <p><i class="fas fa-shield-alt"></i> Sistema de Chamados Técnicos &copy; 2025 - Todos os direitos reservados</p>
        <p>Desenvolvido para suporte eficiente pelo Nicolas e Emerson</p>
    </footer>

    <script>
        document.getElementById('chamadoForm').addEventListener('submit', function(e) {
            e.preventDefault();
            
            // Coletar dados do formulário
            const nome = document.getElementById('nome').value;
            const contato = document.getElementById('contato').value;
            const tecnicoSelect = document.getElementById('setor');
            const tecnicoNome = tecnicoSelect.options[tecnicoSelect.selectedIndex].text.split(' - ')[0];
            const tecnicoPhone = tecnicoSelect.options[tecnicoSelect.selectedIndex].dataset.phone;
            const categoria = document.getElementById('categoria').value;
            const urgencia = document.getElementById('urgencia').value;
            const descricao = document.getElementById('descricao').value;
            
            // Validar se um técnico foi selecionado
            if (!tecnicoPhone) {
                alert('Por favor, selecione um técnico responsável.');
                return;
            }    
            // Formatar a mensagem
            const mensagem = `*🚨 NOVO CHAMADO TÉCNICO*\n\n` +
                             `Solicitante: ${nome}\n` +
                             `Contato:${contato}\n` +
                             `Técnico Responsável:${tecnicoNome}\n` +
                             `Categoria:${categoria}\n` +
                             `Urgência:${urgencia}\n\n` +
                             `Descrição do Problema:\n${descricao}\n\n` +
                             `_Chamado registrado via Sistema de Chamados Técnicos_`;
            
            // Codificar a mensagem para URL
            const mensagemCodificada = encodeURIComponent(mensagem);
            
            // Gerar link do WhatsApp
            const urlWhatsApp = `https://wa.me/${tecnicoPhone}?text=${mensagemCodificada}`;
            
            // Abrir o WhatsApp
            window.open(urlWhatsApp, '_blank');
            
            // Feedback para o usuário
            alert(`✅ Chamado ${numeroChamado} registrado com sucesso! \n\nVocê será redirecionado para o WhatsApp do técnico ${tecnicoNome}.`);
            
            // Limpar o formulário (opcional)
            // this.reset();
        });
        
        // Atualizar indicador de urgência
        document.getElementById('urgencia').addEventListener('change', function() {
            const urgencyText = document.getElementById('urgencyText');
            const urgencyIcon = document.getElementById('urgencyIcon');
            
            switch(this.value) {
                case 'Baixa':
                    urgencyText.innerHTML = '<span class="urgency-low">Baixa prioridade - Atendimento em até 48h</span>';
                    urgencyIcon.innerHTML = '<i class="fas fa-check-circle urgency-low"></i>';
                    break;
                case 'Média':
                    urgencyText.innerHTML = '<span class="urgency-medium">Média prioridade - Atendimento em até 24h</span>';
                    urgencyIcon.innerHTML = '<i class="fas fa-exclamation-circle urgency-medium"></i>';
                    break;
                case 'Alta':
                    urgencyText.innerHTML = '<span class="urgency-high">Alta prioridade - Atendimento em até 4h</span>';
                    urgencyIcon.innerHTML = '<i class="fas fa-exclamation-triangle urgency-high"></i>';
                    break;
                case 'Crítica':
                    urgencyText.innerHTML = '<span class="urgency-critical">URGÊNCIA CRÍTICA - Atendimento imediato</span>';
                    urgencyIcon.innerHTML = '<i class="fas fa-skull-crossbones urgency-critical"></i>';
                    break;
                default:
                    urgencyText.textContent = 'Selecione o nível de urgência';
                    urgencyIcon.innerHTML = '<i class="fas fa-info-circle"></i>';
            }
        });
        
        // Menu mobile
        document.querySelector('.mobile-menu-btn').addEventListener('click', function() {
            const navMenu = document.getElementById('navMenu');
            navMenu.classList.toggle('active');
        });
    </script>
</body>
</html>
