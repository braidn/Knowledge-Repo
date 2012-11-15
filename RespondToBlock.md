    respond_to do |format|
      format.html { render_to products_url }
      format.json { head :ok }
    end