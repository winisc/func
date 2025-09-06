    # Verifica se a situacao_termo possui True 
    if True in situacao_termo:
        # Move os termos para a pasta principal de termos
        movePasta(
            f'{numero_processo}',
            f'{path_pasta_termos_temp}\\{numero_processo}',
            f'{path_pasta_termos}\\{numero_processo}'
        )
        # Remove a pasta de termos temporária
        pasta_temp = f'{path_pasta_termos_temp}'
        if os.path.exists(pasta_temp):
            shutil.rmtree(pasta_temp)
        if not True in situacao_oficio:
            # Remove a pasta de processo caso nao tenha ofício em nenhum precatório
            if os.path.exists(f'{path_pasta_precatorios}\\{pasta}'):
                shutil.rmtree(f'{path_pasta_precatorios}\\{pasta}')